---
title: "Vim Tricks 3: Using Buffer"
date: 2018-08-21 21:17:53
tags: vim
---

This is a relatively short post about buffers. It will mostly help you with copying and pasting.

# What is the buffer?

When you are editing your file, your last action(s) will be saved in a buffer. Unlike editing in a word document or under any windows systems, it is much more accessible. There are many use cases for it, and we are going to cover some most frequenly used ones.

# Recovering deletion(s)

Say you’ve made a deletion in the file a while back, and now you regret about the decision. It may not be too late yet! Deletions are samved in buffers named in number 1-9 automatically. So if you want to recover the second most recent deletion, do:

> {% kbd &quot %}{% kbd 2 %}{% kbd p %}

Now, if this isn’t actual the one you thought was the second most deletion, you may want to look at the third, the fourth and so on. This is easy to do. If you remember, you can use {% kbd u %} to undo the last change and {% kbd . %} to repeat the last change. Hence, combining with the previous command, you would do

> {% kbd &quot %}{% kbd 2 %}{% kbd p %}{% kbd u %}{% kbd . %}{% kbd u %}{% kbd . %}

which says paste the second buffer and undo it and do paste the third buffer and undo it and paste the fourth buffer.

# Saving contents to buffers

Saving contents to buffers is easy. There are two things you can do: initialize a buffer and append to an existing buffer. There are just two more keys you need to press before you can do your normal yank/delete action.

First, you’ll need to press {% kbd &quot %}. This tells vim to start identifying a buffer. Then, press any preferred letter in a-z (**lower case!**), followed by your yank/delete actions. The content is saved into the buffer named by the letter you’ve just chosen. If you already saved something in a buffer and wish to append to it, the shortcut is the same, except you use the **upper** case letter. To summarize:

* {% kbd &quot %}{% kbd a %}{% kbd y %}: yank and save to buffer a
* {% kbd &quot %}{% kbd A %}{% kbd y %}: yank and append to buffer a

# Retrieving from named buffers

This is similar to what we’ve already shown in Recovering deletion(s), except you swap your number name from 1 to 9 with a buffer name from a to z. For example, to get the contents in buffer a, you would type:

> {% kbd &quot %}{% kbd a %}{% kbd p %}

# Reference

1. Arnold Robbins, Linda Lamb, and Elbert Hannah. 2008. Learning the Vi and Vim Editors (Seventh ed.). O’Reilly.

