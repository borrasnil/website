---
title: Rust related blogs - Nil Borras
---

# Rust related blogs
This page will work as a index for all my rust related blogs i create.

# Index 

- [Rust_lazylock]( 2026-11-19-rust_lazylock)
- [Rust_niche_filling]( 2026-11-19-rust_niche_filling)


# Cool trick i use
Since I am serving static HTML files everytime I decide to create a new blog I need
to edit this file and add a new item to the idex list.\
So I came with a simple solution using VIM!\

You can use `<C-r>=system('ls')` to add the stdout of ls into the file. With this and 
filtering "rust" with grep i can add all files that contain "rust" in their name to this 
file.\

Then i use a custom VIM command to execute the motions

```vim
gg/# Index<CR>2jmacis<C-r>=system('ls blog/ | grep rust')<CR>'aVis

"Norm function for formatting
:'<,'>:norm yyPJI- [^[ld6wgUlf.c2w](^[[3~^[A)
```

