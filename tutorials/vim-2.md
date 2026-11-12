---
title: Movement and deletion - How to VIM
---

# How to VIM - Movement and deletion
This guide will cover basic movement and deletion.

> This guide has been heavily inspired by `vimtutor`

## Lesson 1.2.1: Moving between words
- Use `w` to jump to the start of the next word.
- Use `b` to jump to the start of the last word.
- Use `e` to jump to the end of the next word.

- Use `W` to jump to the start of the next full word.
- Use `B` to jump to the start of the last full word.
- Use `E` to jump to the end of the next full word.

> What are full words? A simple word would be `house` whilst a full word is separated by a whitespace

---

## Lesson 1.2.2: Replace and delete characters
- Use `r` to replace the current cursor character.
- Use `x` to delete the current cursor character.
- Use `R` to enter replace mode, all characters you type will replace others.

---

## Lesson 1.2.3: The delete command
VIM is full of bindings, you cast expresions rather than typing random characters.
- Use `dd` to delete a line.
- Use `dw` to delete untill next word.

You can do `de` to (d)elete till the (e)nd of the word.\
Same works with `dB` (d)elete till the (B)egining of last full word.

---

## Lesson 1.2.4: Change
- Use `cc` to delete the current line and enter insert mode.
- Use `cw` to delete untill the next word and enter insert mode.

---

## Lesson 1.2.5: Arround and inner
Now if you used any of the commands listed on the last lesson you would realise you need to go to the begining of a word to delete it with `dw`.\
This is where the arround and inner commands come in.\
We can use them after a verb like delete to modify the funcitonality of it.

- Use `diw` to (d)elete (i)nner (w)ord.
- Use `daw` to (d)delete (a)rround (w)word.

- Use `ciE` to (c)hange (i)nner (E)end.
- Use `cb` to (c)hange till the (b)egining of last word.

> Imagine we have a quoted word "apple" `diw` would leave `""` and `daw` would delete the quotes too.

---

# Lesson 1.2.x Summary
1. Use w, e, b for movement between words.
2. Use r, x, R to replace or delete single characters.
3. Use d followed by a movement or `dd` to delete the current line.
4. Use c followed by a movement or `cc` to delete the current line and enter insert mode.
5. Use a, i as modifiers for commands like delete or change.
