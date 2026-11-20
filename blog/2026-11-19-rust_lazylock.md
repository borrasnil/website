---
title: LazyLock in Rust
---

# LazyLock in Rust
In this blog I will be covering the `LazyLock` type and its uses. I came
around with this type a few times writing my rust projects and I wanted to
write a blog about it since i find it cool.

## What is LazyLock?
LazyLock is a rust static thread-safe type that was introduced in Rust 1.80.
LazyLock wraps a `FnOnce()` and initializes it on first access.

## Lock Poisoning
If the initialization closure passed to `LazyLock::new()` panics,
the lock will be poisoned.\
Once the lock is poisoned any threads that try to acces it will panic too.

## Definition
This is the definition of `LazyLock`
```rust
pub struct LazyLock<T, F = fn() -> T> {
    once: Once,
    data: UnsafeCell<Data<T, F>>,
}
```

As seen in the definition `LazyLock` wraps around `Once` and an `UnsafeCell` 
with two generic types. Once is a low-level synchronization primitive for one-time 
global execution. This type is used to store the state of the lock.
- T is the type that will be returned
- F is the closure you pass into it

The data structure definition is the following:
```rust
union Data<T, F> {
    value: ManuallyDrop<T>,
    f: ManuallyDrop<F>,
}
```

The first call to `call_once` F is taken and run. If it succeeds `value` is set
and the state is changed to "complete". If it panics, the Once is poisoned as
explained earlier, so none of the two fields is initialized.

So the overview execution is:
1. Create a LazyLock and pass a closure 
2. Struct is created and `once` is set to "incomplete" 
3. The lock is called and the closure is ran
4. If the closure panics set `once` to "poisoned"
5. The closure resolves `value` inside of `data`

---

# Examples
Initialize static variables with `LazyLock`, this example uses the `dirs` crate
```rust
use std::sync::LazyLock;

static CONFIG_PATH: LazyLock<PathBuf> = LazyLock::new(|| {
	dirs::config_dir().expect("Could not find config directory")
		.join("myapp")
		.join("myapp_config.json")
});

let _ = &*CONFIG_PATH;
```

# Conclusion
LazyLock is a synchronization primitive that provides safe, lazily-initialized 
global state. Other use cases where might be useful would be:
- Regex compilation, avoid recompiling per call
- Heavy objects that you want initialized on first use rather than at startup
- Shared expensive lookup tables
- Initializing a global subscriber for logging / tracing
- Paths or environment variables
