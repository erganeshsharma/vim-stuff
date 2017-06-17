# Vim Basic Tutorials

Vim is a very powerful editor that has many commands, too many to explain in a tutor such as this.
This tutor is designed to describe enough of the commands that you will be able to easily use Vim as an all-purpose editor.
---
##### Starting Vim
- To start Vim from the shell prompt type:  `$ vim FILENAME <ENTER>`
##### Moving Cursor
- The cursor is moved using either the arrow keys or the hjkl keys.
    `h` (left)    `j` (down)    `k` (up)      `l` (right)
##### Text Editing - Insertion and Appending
- To insert or append test type:
    * `i`   type inserted text	`<ESC>`	insert before the cursor.
    * `A`   type appended text	`<ESC>`	append after the line.
##### Text Editing - Deletion
- To delete the character at the cursor type:  `x`
##### Exiting Vim
- To exit Vim type:
    * `<ESC>	:wq	<ENTER>` to save the changes and quit.
    * `<ESC>	:q!	<ENTER>` to trash all changes and quit.
>**NOTE:** Pressing `<ESC>` will place you in Normal mode or will cancel an unwanted and partially completed command.
---
##### Deletion Commands
- To delete from the cursor up to the next word type: `dw`
- To delete from the cursor to the end of a line type: `d$`
- To delete a whole line type: `dd`
##### On Operators and Motions
- To repeat a motion prepend it with a number: `2w`
- The format for a change command is:
    `operator [number] motion`
    where:
	    `operator` - is what to do, such as `d` for delete.
	    `[number]` - is an optional count to repeat the motion.
	    `motion`   - moves over the text to operate on, such as `w` (words), `$` (to the end of line), etc.
- To move to the start of the line use a zero: `0`
##### The Undo Command
- To undo previous actions, type: `u` (lowercase u)
- To undo all the changes on a line, type: `U` (uppercase U)
- To undo the undo's(redo), type: `CTRL-R`
---
##### The Put Command
- To put back text that has just been deleted, type `p`. This puts the deleted text AFTER the cursor (if a line was deleted it will go on the line below the cursor).
##### The Replace Command
- To replace the character under the cursor, type `r` and then the character you want to have there.
##### The Change Operator
- The change operator allows you to change from the cursor to where the motion takes you. eg. Type `ce` to change from the cursor to the end of the word,  `c$` to change to the end of a line.
- The format for change is:
	    `c [number] motion`
---
##### Cursor Location and File Status
- `CTRL-G` displays your location in the file and the file status.
- `G` moves to the end of the file.
- `number G`  moves to that line number.
- `gg`  moves to the first line.
##### The Search Command
- Typing `/` followed by a phrase searches **FORWARD** for the phrase.
- Typing `?` followed by a phrase searches **BACKWARD** for the phrase.
- After a search type `n` to find the next occurrence in the same direction or `N` to search in the opposite direction.
- `CTRL-O` takes you back to older positions, `CTRL-I` to newer positions.
##### Matching Parenthesis Search
- Typing `%` while the cursor is on a `(,),[,],{, or }` goes to its match.
##### The Substitute Command
- To substitute new for the first old in a line type `:s/old/new`
- To substitute new for all 'old's on a line type `:s/old/new/g`
- To substitute phrases between two line #'s type `:#,#s/old/new/g`
- To substitute all occurrences in the file type `:%s/old/new/g`
- To ask for confirmation each time add 'c' `:%s/old/new/gc`
---
##### To Execute an External Command
- `:!` command executes an external command.
Some usefule examples are :
    * `:!ls` shows a directory listing.
    * `:!rm FILENAME` removes file FILENAME.
##### Writing Files
- `:w FILENAME` writes the current Vim file to disk with name `FILENAME`.
##### Selecting Text to Write
- `v`  motion  `:w FILENAME`  saves the Visually selected lines in file `FILENAME`.
##### Retrieving and Merging Files
- `:r FILENAME` retrieves disk file `FILENAME` and puts it BELOW the cursor position.
- `:r !ls` reads the output of the `ls` command and puts it BELOW the cursor position.
---
##### The Open Command
- Type `(lowercase) o` to open a line **BELOW** the cursor and start Insert mode.
- Type `(uppercase) O` to open a line **ABOVE** the cursor.
##### The Append Command
- Type `(lowercase) a` to insert text **AFTER** the cursor.
- Type `(uppercase) A` to insert text **AFTER** the end of the line.
- The `e` command moves to the end of a word.
##### Another Way to Replace
- Typing a capital `R` enters **Replace** mode until `<ESC>` is pressed.
##### Copy and Paste Text
- The `y` operator yanks (copies) text, `p` puts (pastes) it.
##### Set Option
- Typing `":set xxx"` sets the option `"xxx"`.
Some options are:
    * `'ic' 'ignorecase'` ignore upper/lower case when searching.
    * `'is' 'incsearch'` show partial matches for a search phrase.
    * `'hls' 'hlsearch'` highlight all matching phrases.
You can either use the long or the short option name.
- Prepend `"no"` to switch an option off : `:set noic`, `:set nohlsearch`, etc
---
##### Getting Help
- Type `:help`  or  press `<F1>` or `<Help>` to open a help window.
- Type `:help cmd` to find help on cmd.
- Type `CTRL-W CTRL-W` to jump to another window.
- Type `:q` to close the help window.
##### Create a Startup Script
- Create a **vimrc** startup script to keep your preferred settings.
##### Completion
- When typing a  `:` command :
    * press `CTRL-D` to see possible completions.
    * Press `<TAB>` to use one completion.
---
##### Further Reading
- For Further Reading and Studing, this book is recommended: `Vim - Vi Improved - by Steve Oualline`.
- To try these tutorials interactively, use : `$vimtutor` command on a shell terminal.
- To exit from the `vimtutor` press `<ESC>` and then `:q`.

This tutorial was written by Michael C. Pierce and Robert K. Ware,
Colorado School of Mines using ideas supplied by Charles Smith,
Colorado State University. E-mail: bware@mines.colorado.edu.
Modified for Vim by Bram Moolenaar.
---