# Moving around in Vim with keyboard shortcuts

## Moving Around
Vim lets you to navigate in a file by using keyboard shortcuts.

When you master these shortcuts, you won't want to use any other command line editor.

Let's dive in!

 

First generate a file to work on with 100 lines:

`for i in {1..100}; do echo "This is line $i" >> new-file; done`
Open the file that you created:

`vim new-file`
Vim has multiple nodes, but we will focus first to normal mode

This mode is the default mode and it can always be activated by pressing `Esc`

In Vim, almost all operation commands are performed in normal mode

Important Note: you can undo whenever you need it in normal mode by pressing u

 

Press `Esc` and type `:set number` to show the line numbers

You can move to a line by just entering the line number in normal mode

Type `:30` to jump to line 30

It is also possible to jump directly to a character in a file

Type `:goto 700` to jump to 700. character


## Keyboard Shortcuts
There are several keyboard shortcuts to navigate in a file

To get to the last line, enter `]]` or `G`

To get to the first line, enter `[[` or `gg`

 

Use keyboard shortcuts below to play around and get familiar:

Shortcut Key	Function
Ctrl + f		moves the cursor one page down
Ctrl + b		moves the cursor one page up
h				moves the cursor one character to the left
j or Ctrl + J	moves the cursor down one line
k or Ctrl + P	moves the cursor up one line
l				moves the cursor one character to the right
0				moves the cursor to the beginning of the line
$				moves the cursor to the end of the line
^				moves the cursor to the first non-empty character of the line
w				move forward one word (next alphanumeric word)
W				move forward one word (delimited by a white space)
5w				move forward five words
b				move backward one word (previous alphanumeric word)
B				move backward one word (delimited by a white space)
5b				move backward five words
