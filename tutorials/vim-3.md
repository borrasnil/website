# How to VIM - Visual mode & motions
This chapter will explain how to use visual mode.

> This guide has been heavily inspired by `vimtutor`

## Lesson 1.3.1: Visual operator
Visual mode would be your normal selection mode in any text editor.
- Use `v` to enter VISUAL mode.

Now move the cursor with the learned motions, you see the selection grows.

---

## Lesson 1.3.2: Visual lines mode
But what if you want to select entire lines.
- Use `V` to enter VISUAL LINES mode.

---

## Lesson 1.3.3: The Open operator
- Use `o` to create a new line under the cursor.
- Use `O` to create a new line on top of the cursor.

```
 <--- O        
James sat down on his computer and then learned VIM.
 <--- o
```

---

## Lesson 1.3.4: Operating on lines
VIM is full of useful motions such as:
- The `0` motion jumps to the start of the line.
- The `$` motion jumps to the end of the line.

> These kinds of motions are really useful paired with motions such as `d$` (deletes till the end of the line)

---

## Lesson 1.3.5: File movement
- Use `G` to move the cursor to the end of the file.
- Use `gg` to move the cursor to the start of the file.

---

## Lesson 1.3.6: Using a count for a motion
It is possible to pair a motion with a count to repeat X times.
- Use `2dw` to delete two words from cursor.
- Use `14j` to go down 14 lines form cursor.

---

# Lesson 1.3.x Summary
1. Use `v` to enter VISUAL mode.
2. Use `V` to enter VISUAL LINE mode.
3. Use `o` and `O` to create new lines.
4. Use `0` and `$` to move to the start/end of the line.
5. Use `G` and `gg` to move to the start/end of the file.
6. Use a count to repeat a motion X times.

### Next chapter
[How to VIM - Yanking and pasting](vim-4)
