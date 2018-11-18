---
title: "Vim Tricks 1: Basic editing"
date: 2018-08-17 19:00:23
tags: vim
---

In this post, I’m going to cover some basic functionalities of vim which will help you to get started. Like LaTeX, which alleviates the author’s burden on formating, vim will help you to focus on your programming by providing a wide range of shortcuts that improve your editting efficiency.

# Command and editing modes
Before we start, it’s important to note that vim is not like your other text editors. It has two modes: insert (editing) and command mode. You type in the material you want in insertion mode, and you use commands to change your content “systematically” in the editing mode. We are going to cover more of this later.

# Moving around

## Replacement for the arrow keys

In vim, you dont move around by the arrow keys or the mouse. They are too far away from the center of your editing panel, the a-z’s. Also, because of the two editing mode, we’ve doubled the function of each key. Therefore,

{% kbd h %} left, {% kbd h %} down, {% kbd k %} up, {% kbd l  %} right

are used for moving around in the command mode. Once you get used to it, you’ll find it intuitive and much more convenient than the arrow key.

## Cursor movements: what the arrow keys can’t do

Beyond what’s simply moving up and down, left to right, there are a lot more cursor movements you’ll be able to do in vim.

* Word movements

    * {% kbd w %}{% kbd W %} beginning of next word
    * {% kbd e %}{% kbd E %} end of next word
    * {% kbd b %}{% kbd B %} go back to the beginning of the previous word

The difference between to lower case and upper case is, the lower cases treat symbols as words while the upper case doesnt.

* Line movements

    * {% kbd 0 %}{% kbd $ %} beginning/end of the line
    * {% kbd + %}{% kbd - %} first character of next/previous line
    * {% kbd 1-9 %}{% kbd G %} go to line number, line number followed by G

# Editing text

Now you know how to move around, you’ll need the insert mode to get your content going. To switch to insert mode, you’ll need to press certain keys in command mode. These key will move your cursor and switch your mode.

* Word editing

    * {% kbd i %}  insert will let you insert text at the current cursor position
    * {% kbd a %} append will let you insert text after the current cursor position (moves it right by 1 place)
    * {% kbd x %} removes the character unber cursor (cross out)
    * {% kbd r %} replace the character under the cursor by another character. It will exit insert mode as soon as you’ve finished the replacement.
    * {% kbd ~ %} Toggle case
    * {% kbd v %} Visual mode for moving the cursor and selecting text

* Line editing

    * {% kbd o %}{% kbd O %} open new line below/above
    * {% kbd S %} delete line and Substitute text
    * {% kbd I %} Insert at beginning of line
    * {% kbd A %} Append text at end of line
    * {% kbd R %} Rplace mode, overstrike existing characters with new text
    * {% kbd J %} Join current and next line
    * {% kbd V %} Select entire line

* Commands

    * {% kbd y %} Yank (copy)
    * {% kbd p %} paste
    * {% kbd u %} undo
    * {% kbd Ctrl %}{% kbd R %} Redo
    * {% kbd p %} paste
    * {% kbd d %} delete
    * {% kbd c %} change word

# Combining numbers with commands
You can often combine numbers, with commands, and then even with commands again. Here, we’ll just provide some examples.

* `5 i hello world esc` will insert hello world 5 times once you press esc to exit from the insert mode.
* `3 k` will move your cursor up 3 lines.
* `2 d w` will delete the next two words.
* `d $` wll delete from the cursor to the end of the line.


In short, the first number is the number of repetitions you want vim to perform on the following command. Then you can combine commands together.

# Miscellaneous

## Ex mode
If you don’t know, Ex is a direct predecessor of vim. You can use Ex commands in the command mode by typing {% kbd : %}.

* `:set nu` turns on line numbers. :set nonu turns it off.
* `:set tw=79` automatically wraps your line before the 79th character
* `:w` save
* `:q` quit
* `:wq` save and quit

# Reference

1. Arnold Robbins, Linda Lamb, and Elbert Hannah. 2008. Learning the Vi and Vim Editors (Seventh ed.). O’Reilly.