### Search and Replace Operations in Vim

Search in Vim
Searching text in a file is a very common task.

Vim allows you to search for a file by using / (forward slash) to search forward and ? (question mark) to search backward in a file. Let's try it out.

Important Note: you can undo whenever you need it in normal mode by pressing u

 

First generate a file to work on with 100 lines:

for i in {1..100}; do echo "This is line $i" >> new-file; done
Open the file that you created:

vim new-file
Basic Search

Type / to enable search mode and type li and press enter

You will notice that the cursor points out the nearest matching string

Press n to jump to the next occurrence or N to jump to the previous occurrence

Next, type ? to enable search mode again but backwards this time and type li

Press n or N to jump to the next occurrence and notice that it will go backwards

You can use up/down arrow keys when you are in search mode to display your previous search strings

 

Search Entire Word

As you may notice, search command looks for a string pattern, not the entire word

To search the whole word, you need to enter /\<line\> to find line in the file

Vim allows us to start a search for the current word that the cursor is pointing

Type / to enable search mode and type li

Now, press * (asterisk) to search the entire word which is line in our case

You can also press # (hash) to search backwards

 

Ignore Case

By default search is case-insensitive. It is possible to ignore case in a search by adding \c to the end of your search string

Type / to enable search mode and type this

It won't return any results

Type / again and type this\c this time and notice that search finds string This which has a capital letter

You can also ignore case indefinitely for the current session

Type :set ignorecase or :set ic

To revert it back, Type :set noignorecase or :set noic

To make it default for vim, you need to add it to ~/.vimrc file

 

Press Esc and type :q! to quit without saving



## Find and replace
You will often need to find and replace a string in a file.

There is a command to do that in the whole form:

:[range]s/{pattern}/{string}/[flags] [count]
Vim lets you also use a different delimiter instead of / if you have it already in your search pattern. For example: :s|foo|bar|

Please note that given parameters shown in brackets are optional. Let's try it out.

 

Open the file that you created:

vim new-file
In normal mode, type :s/line/row/

Notice that the first occurrrence of string line is replaced

To replace all occurrences in a line, you would use :s/line/row/g

But the result won't change in our case, because we have the string line only once in each line

Add same string multiple times in a line and try it out if you wish

 

When you want to find and replace all occurrences of a string in entire file, you need to use % (percentage character) in front of s to define the complete range

Type %s/line/row/g and notice that all occurrences of line have been replaced in the file

 

Ignore Case

To ignore case in your search, use the i flag:

Type :%s/this/that/gi to replace all occurrences of this case insensitively with that

 

Search Range

We can define a range of line by just giving it with a , (comma character) before s :

Type :5,10s/line/LINE/g to replace all occurrences of line with LINE

. (dot character) indicates the current line and $ the last line

Type :.,$s/this/those/i to replace all occurrences of this with those from the current line to the end of the file. i is added to ignore case in the search

 

You can test out a few different find and replace scenarios below

First type :q! to quit without saving and open the file again with its initial version:

vim new-file
 

Case: Get to line 50 and replace all occurrences of This with That starting from the current line up to next 5 line

Type :50 to get to line 50 and type :.,+5s/this/That/i

Case: Comment out the lines between 20-30 (in Vim you put a # in the beginning of a line to comment out as in python)

This is particularly important when you are dealing with configuration files in linux

Type :20,30s/^/# / as ^ denotes the beginning of a line

Type :20,30s/^# // to uncomment them