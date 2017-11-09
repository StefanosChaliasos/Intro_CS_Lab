# VIM cheatsheet for beginners

### Getting started:
* Open/Create a file with VIM: `vim filename.txt`
* Insert Mode: `i`
* Normal Mode: `Esc`
* Command Mode: `Esc`
* Last Line Mode: `:<command>`

### Last Line Mode Basics:
In order to use last line mode you need to press the  key  "`:`".
* Saving your file without quit (write): `:w`
* Saving your file and quit (write and quit): `:wq`
* Quit without saving: `:q!`

### VIM Basic Insert Commands:
* `i`: insert at the current position
* `I`: insert at the beginning of line
* `a`: append just after the current cursor position
* `A`: append at the end of line
* `o`: Open a new line below the current line
* `O`: Open a new line above the current line

(In order to use the commands above make sure you are in Command Mode)

### Navigation and Basic Movement:
* `h`: left
* `l`: right
* `j`: line down
* `k`: line up
* `w`: word/token on the right
* `b`: word/token on the left

**NOTE**:
> You can use the commands above in combination with numbers like 2, 6, 18 etc. When you do so you get as result the repetion of the selected command as many times as the number you used. For example the command `3w` will move the cursor 3 words/tokens right.

(In order to use the commands above make sure you are in Command Mode)

### Basic Commands for Deletion:
* `x`: Delete
* `X`: Backspace
* `dd`: deletes a line
* `d` + navigation character (`h`, `l`, `j`, `k`): deletes on a certain direction (specified by navigation character)

(In order to use the commands above make sure you are in Command Mode)
