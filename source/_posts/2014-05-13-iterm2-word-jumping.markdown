---
layout: post
title: "iTerm2 word jumping"
date: 2014-05-13 13:15
comments: true
categories: Programming
---

I’m so tired of looking for posts about jumping/deleting words and jumping between the beginning and the end of the line in iTerm2, that I’ve decided to write my own post.

### Word jumping – with option + left/right

- Go to iTerm preferences –> “your default profile” –> Keys
- get rid of the lines with the two lines sending escape codes with option + left/right
- Add a couple of lines in iTerm preferences –> Keys (Global Shortcut keys)
    - option + left: Send Escape Sequence, ESC + B
    - option + right: Send Escape Sequence, ESC + F

### Word deletion – with option + backspace

Add a line in iTerm preferences –> Keys (Global Shortcut keys):

- option + backspace: Send Hex Code, 0x1B 0x08

### Jump to the beginning/end of a line – with cmd + left/right

Add a couple of lines in iTerm preferences –> Keys (Global Shortcut keys):

- cmd + left: Send Hex Code, 0x01
- cmd + right: Send Hex Code, 0x05

Check the following screenshot for more details:

![Screen shot](https://lh3.googleusercontent.com/-i9gBv_w7PkE/U3IUEQ8mUUI/AAAAAAAAO9U/8oUtFFLcSiI/w922-h539-no/Screen+Shot+2014-05-13+at+13.45.12.png)
