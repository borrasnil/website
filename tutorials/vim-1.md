---
title: Basic Usage - How to VIM
---

# How to VIM - Basic usage
This first chapter will cover how to use VIM on its most surface level.

> This guide has been heavily inspired by `vimtutor`

## Lesson 1.1.1: Moving the cursor
To move the cursor press h, j, k ,l as follows:
```
        ^            
        k             The `h` key moves the cursor left
                      The `j` key moves the cursor down
                      The `k` key moves the cursor up
 < h         l >      The `l` key moves the cursor right


        j
        v
```

---

## Lesson 1.1.2: Basic commands
Type `:` to execute a command in VIM.
In VIM there are multiple ways of doing the same task, same applies to exiting it:
- Type `:q` to quit.
- Type `:w` to write changes.
- Type `:wq` to write changes and quit.
- Type `:x` to write changes and quit.
- Type `<Ctrl>zq` to quit.
- Type `<Ctrl>zz` to write changes and quit.

Dont be overwhelmed by the possibilities or what option to use, they are all valid.

---

## Lesson 1.1.3: VIM modes
The thing that differenciates VIM from your average text editor are modes, there are multiple modes:
- NORMAL 	(default: this is where you perform VIM bindings)
- INSERT	(this would be your normal text editor)
- VISUAL	(used for selections)

To enter normal mode again by just pressing `<ESC>`

---

## Lesson 1.1.4: Insertion and Appending
- Press `i` to enter INSERT mode before your cursor.
- Press `a` to enter INSERT mode after your cursor.
- Press `I` to enter INSERT mode at the begining of the line.
- Press `A` to enter INSERT mode at the end of the line.

> Remember you can get back on normal mode with `<ESC>`

# Lesson 1.1.x Summary
1. The cursor is moved using h, j, k, l
2. Type `:q` to quit and `:w` to save.
3. There are three different VIM modes, you cant type on your file in NORMAL mode.
4. Use `i` and `a` to enter INSERT mode.

### Next chapter
[How to VIM - Movement and deletion](vim-2)
