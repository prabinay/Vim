# Text manipulation operations in Normal & Insert mode

## Vim modes
Vim has multiples modes to operate. We will focus on the most used ones as listed below:

Mode	Description
Normal	Default mode for navigation and manipulation of text and it can always be activated by pressing Esc
Insert	Used for inserting/manipulating the text by using all keyboard keys. Not any Normal mode commands is active in this mode
Visual	Used for navigation and manipulation of text selections. Allows the use of most Normal mode commands on selected text
It is important to note that, in Vim, almost all operation commands are performed in Normal mode
In this scenario, we are going to install some vim plugins to change the visual appearance of vim, to be able to better understand how modes are functioning:

git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime

sh ~/.vim_runtime/install_awesome_vimrc.sh


## Insert mode intro
We've covered most functionalities of Normal mode in previous scenarios

Let's focus on Insert mode and create a new file with some content to work on:

cat << EOF > new-file
Hello World,
This exercise is awesome!
EOF
Open the file that you created:

vim new-file
You will notice that vim has a different appearance than before
Click i to activate Insert mode. You can add/delete text as you want

Press Esc and press u to undo your last change

 

There are also another ways to activate Insert mode:

Command	Description
o	Insert new line below the current line and switch to insert-mode
O	Insert new line above the current line and switch to insert-mode
a	Append after cursor and switch to insert-mode
A	Append at end of line and switch to insert-mode
s	Delete the character cursor is currently on and switch to insert-mode
C	Delete all after cursor position and switch to insert-mode
 

Try it out and when you are ready:

Press Esc and type :q! to quit without saving



## Text manipulations - Delete
Manipulating text in Vim with some handy commands in Normal mode can save you a tons of time.

Let's create a longer text file with more content:

cat << EOF > long-file
Hello World,
This exercise is still awesome!
I am learning a lot
I want to be a Vim master
And I'm feeling that I am very close to my goal!
Let's see if this text is long enough 
EOF
Open the file that you just created:

vim long-file
First type :set number to show the line numbers

Type O to enter a new line on top by switching to insert mode and write some text

 

Delete

Press Esc and type dd to delete the line

Press u to undo your changes and make sure that you are still on line 1 (You can always type gg to get to the top)

Type 3d and press Enter to delete the first 4 lines. Notice that deleting is a 0 indexed operation with d command so try with 1d and notice that it will remove 2 lines below

Type D to remove the content of the line but not the line itself

Delete all lines in Vim

Type gg to get to first line

Type dG to clear the file completely

 

You can just try out more sophisticated delete operations:

Command	Description
d<left-arrow>	Delete current and left character
d<right-arrow>	Delete current and right character
d<up-arrow>	Delete current and upper line
d<down-arrow>	Delete current and bottom line
d$	Delete from current position to end of line
d^	Delete from current backward to first character
dO	Delete from current backward to beginning of line
dw	Delete current to end of current word
db	Delete current to beginning of current word
 

Try it out and when you are ready:

Press Esc and type :q! to quit without saving


## Text manipulations - Copy, Cut & Paste
Let's continue with copy, cut & paste commands in Vim

Open long-file that you created:

vim long-file
First type :set number to show the line numbers

Type G to get to the end of the file and type o to enter a new line by switching to Insert mode and write some text

Copy, Cut & Paste

Press Esc and type yy to copy the line (y is short for yank)

Type :2 to jump to line 2 and type p to paste the content to line 3

Repeat the operation by pressing dd to cut a line and p to paste the content
 

Type :u0 to undo all changes since opening to reset

Type :4 and get to line 4 and type 3yy to copy the current and next 2 lines

Type gg to get to the top and type P to paste these 3 lines before the cursor

Replace 3yy with 3dd to cut instead of copy and reply the operation if you wish

 

Again, refer to the table below for more sophisticated copy operations in Vim

Command	Description
y$	Copy all from current to end of line
y^	Copy all from current to start of line
yw	Copy to the start of next word
yiw	Copy the current word



