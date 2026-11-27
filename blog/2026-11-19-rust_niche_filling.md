---
title: Niche filling in Rust
---

# Niche filling in Rust
While reading the Rust for Rustaceans book I came along a topic known as "niche filling". This is a compiler optimization
used to reduce memory usage on types like `Option. \ 
> _Then a channel i follow on youtube uploaded a video about it, go watch it, the creator does a really nice job explaining it._
> _[Niche filling: Rust's most satisfying optimization](https://youtu.be/Wg8fFrIsyuI?si=_4hrqyxz3DZYkBrB)_

## What is niche filling?
As mentioned before nice filling is a type of optimization the rust compiler does. The rust compiler is full with
small optimizations like this one but the idea behind niche filling really stuck to me when i learned about it.


## Definition
Before any further explanation on niche filling we need to know how the `Option` type works in rust. This type lets us 
pass in a value that migth be `None` or `Some(T)` the definition looks like this:

```rust
pub enum Option<T> {
    None,
    Some(T),
}
```

The type Òption<T>` needs a way to represent `None`, the first approach is to store a tag byte saying witch variant
it is plus padding for values. But rust takes a different aproach, there are some types that can never reach a value, 
for example the `bool` type takes one byte, but only has two possible states.

```
0x00000000 // true
0x00000001 // false
```

Niche filling gets `0x00000002` as `Option::None` to save up a byte in memory.


---

# Examples
The `NonZeroU8` type from the `std::num` crate or other non zero types also benefits from niche filling, 
as the name suggest this type cant be equal to zero. This type has the same size and aligment as `u8` and 
you can check this with a simple assert:

```rust
use std::num::NonZeroU8;

assert_eq!(size_of::<NonZeroU8>(), size_of::<Option<NonZeroU8>>());
assert_eq!(align_of::<NonZeroU8>(), align_of::<Option<NonZeroU8>>());
```

# Conclusion
Nice filling is one of many optimizations the rust compiler has, optimizing codebases to the last byte is what
enables rust to get 
