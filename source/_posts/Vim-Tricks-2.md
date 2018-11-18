---
title: "Vim Tricks 2: More editing tricks"
date: 2018-08-19 19:36:03
tags: vim
---

Now that you’ve learned the basics, you should start practicing these skills by using Vim as your primary text editor. In this post, we are going to go through more tricks with regards to moving around.

# Screen tricks

What you can see in your editor is called a “screen”. Obviously, a long file can have contents that spans several “screen”s and you’ll need to be able to move around them. Some useful commands are:

* {% kbd ctrl %}

    * {% kbd ctrl %} {% kbd F %} Foward one screen
    * {% kbd ctrl %} {% kbd D %} Move Down half screen
    * {% kbd ctrl %} {% kbd B %} Backward one screen
    * {% kbd ctrl %} {% kbd U %} Move Up half screen
    * {% kbd ctrl %} {% kbd E %} Move down one line
    * {% kbd ctrl %} {% kbd Y %} Move up one line

* Keep cursor in position

    * {% kbd z %}{% kbd enter %} Current line becomes the top line
    * {% kbd z %}{% kbd . %} Current line to the center
    * {% kbd z %}{% kbd - %} Current line to the bottom

# Cursor tricks

Even on the same screen, moving cursor effeciently will be useful. We’ve already covered tricks like {% kbd + %} and {% kbd - %}. Here are some more:

## By screen

* {% kbd H %} Move cursor to Home
* {% kbd M %} Move cursor to Middle
* {% kbd L %} Move cursor to bottom (I use High, Middle and Low to remember these three commands)
* {% kbd enter %} or {% kbd + %} Move cursor to first character of next line
* {% kbd - %} Move cursor to first charcter of previous line
* {% kbd ^ %} Move curosr to first nonblank character of current line
* {% kbd 1-9 %}{% kbd | %} Move to column number of the current line
* {% kbd G %} Go to the end of file
* {% kbd `` %} Move cursor to previous position

## By content

* {% kbd ( %} or {% kbd ) %} beginning of current/next sentence (.?! marks the end of an sentence)
* {% kbd { %} or {% kbd } %} beginning of current/next paragraph (empty line)
* {% kbd [[ %} or {% kbd ]] %} beginning of current/next section

# Searching

Searching a document is perhaps the most common task one performs day to day. Search in Vim supports regex patterns, but we are only goint to cover the bascis here.

* {% kbd / %} or {% kbd ? %} initialize searchs. / does the search forwards, and ? does it backwards. For example, if I want to search the next occurance of “to”, I would type “/ to” and press enter. To find the previous one, I need to type in “? to”.
* {% kbd N %} or {% kbd n %} handles multiple occurances. It repeats the last search in opposite/same direction.

# Reference

1. Arnold Robbins, Linda Lamb, and Elbert Hannah. 2008. Learning the Vi and Vim Editors (Seventh ed.). O’Reilly.