## Open, edit and close a file
Vim has a lot of functionality to make editing very easy for users.

Let's learn your first steps with the console based editor Vim!

 

First open a new file:

`vim my-file`
Next type i to get into the insert-mode. The mode is shown on bottom left

Now type any text, like hello world !

To get into command-mode press `Esc`

To save the file we need to type `:x` and confirm with `Enter`

This will close Vim and we can view the newly created file:

`cat my-file`

## Edit and close a file like a Vim master
You can also type `:wq` to save and quit which is equal to `:x`

If you just want to quit, just type `:q`

type `q!` if you want to quit without saving your changes.

 

Open the file that you just created:

`vim my-file`
Type o to insert new line below the current line by also switching to insert-mode.

Now add some more text to the file, like just landed !

To get into command-mode press `Esc`

To save the file we need to type `:wq` and confirm with Enter

This will close Vim and save the file same as `:x`

 

Open the file again:

vim my-file
press `Esc` and type `:q` without making any changes to quit.

Once again, open the file and make some changes. We want to quit this time with our changes to be ignored.

You'll need to use it often when you accidentally changed in a file.

`vim my-file`
Type O (capital o ) this time to insert new line above the current line and switching to insert-mode.

Now add some text and press `Esc` and type `:q`

Vim doesn't let you to quit because you didn't save your changes.

type `:q!` to override and quit. Any changes you've made will be ignored.