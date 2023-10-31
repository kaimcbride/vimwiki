# NEOVIM NOTES

<span style="color:#cc241d;">aka Neovim Commands I always forget but want to remember</span>

## QUIT
    Rather than :q or :wq or :q! use ZZ

## KEY BINDINGS
    :help index (show all default key bindings)
    :map (show all custom bindings)
    :map <leader> (show all leader bindings)

## NAVIGATION:
    H Top
    M Middle
    L bottom
    f<char> move to the next char in the line
    t<char> move up to but not on that char
    F<char> move back to the next char in the line
    T<char> move backwards to but not on that char
    ; move to the next match from 't' and 'f'
    _ move to the first char in line
    gg Top of file
    G bottom of file
    <num>gg or <num>G jump to that line number
    % move to matching character () {} [] 
    { } Move up and down by paragaph

## SCROLLING
    Cntrl-y scroll up by one line
    Cntrl-f forward one screen
    Cntrl-b backward one screen
    Cntrl-d Move Down but keep cursor in the same spot
    Cntrl-u opposite of Cntrl-d
    zz Center on Cursor Position


## MACRO
    qa # begins recording in register 'a'
    >> record activity <<
    q # stop recording
    @a # run macro in register 'a'

## SEARCH AND REPLACE
    : s/search/replace/ # only on this line
    : %s/search/replace/ # globally in the file
    flags: 
        g multiple accurances on the line
        c confirm
        i case insensitive
    # search backward for item under cursor
    % find the next curly/square bracket on the line

## RUN SHELL COMMANDS
    :! <commands>

## EDIT COMMANDS
    I jump to beginning of line and Insert
    A jump to end of line and Insert
    gu <movement> # lowercase range
    gU <movement> # uppercase range : gUw up the word
    J join the lines
    c <movement> change deletes the range and puts you in edit mode
    xp transpose letters teh-> the 
    {num}>> or {num}<< shift num lines left or right

## VISUAL MODE : Mark lines then do a command
    v enter visual mode with movement
    V enter line visual mode
    Cntrl-v Vertical Column Selection mode
        Select all of the area using Vertical Column. Then 'A' to append to add to the end. Or use 'C' to change, I to insert.
        
    Commands:
    d delete
    y yank
    ~ switch case
    u lowercase
    U uppercase
    a <movement> mark : aw mark word
    A append
    c change

    :w <FILENAME> to write marked lines to a new file



## INCREMENT NUMBERS WITH VISUAL MODE
    use Cntrl-v for vertical selection in Visual Mode
    Select a column of numbers. Cntr-a Cntrl-a to increment by 1
    Even better: g Cntrl-a Cntrl-a and it increments the column
    Cntrl-x to decrement
    foobar[1]  bar[6]
    foobar[1]  bar[7]
    foobar[1]  bar[2]
    foobar[1]  bar[5]
    foobar[1]  bar[6]
    foobar[1]  bar[7]

## WORKING WITH MULTIPLE BUFFERS
    :e <file> opens file in new buffer
    :bn next buffer
    :bp prev buffer
    :b# buffer by number 
    :bd delete buffer
    :ls list buffers

    <leader>fb to use Telescope to find a buffer

    :Ex to explore the directory of the current buffer file 
        <leader>b
    :Sex same as above but opens in split window
    :Rex return to the previous directory explorer

    :r <filename> read in from other file
    :r !<cmd> read in the results of command


## WORKING WITH REGISTERS
    :registers to list out the current values in the regsiters
    "{register_num}p to paste that register value in Normal mode

    To add to a register you can use one of the commands like 'd', 'c', 's',
    'x', 'dd', 'yy' and the like but put "{registernum} first
    ex: "ayy would yank the current line and put it into register a

   When in Insert you can do
     <C-r>{register} to insert the contents of that register
    <C-r>. (the last text that you inserted)
    <C-a> is the same as "<C-r>."
  
## COMPLETION METHODS
  <C-e> Clears completion 

   <C-p>  completion search previous
   <C-n>  completion search next

    <C-x><C-f> filename completion
    <C-x><C-p> Context aware completion. Trick is to not hit space but just
    keep up with <C-x><C-p> and sometimes add the extra <C-p> to select and
    continue. Sick.

    <C-x><C-l> repeat the line
        Cool thing here is like <C-x><C-p> if you continue without a space it
        will start repeating lines after the previous match. 

    <C-x><C-o> omni completion of code

## RANGE
    Specify line ranges with a variety of prefixes to a command
    Some Ex commands accept a line range in front of them.  This is noted as
    [range].  It consists of one or more line specifiers, separated with ',' or
    ';'.



	{number}	an absolute line number  *E1247*
	.		the current line			  *:.*
	$		the last line in the file		  *:$*
	%		equal to 1,$ (the entire file)		  *:%*
	't		position of mark t (lowercase)		  *:'*
	'T		position of mark T (uppercase); when the mark is in
			another file it cannot be used in a range
	/{pattern}[/]	the next line where {pattern} matches	  *:/*
	?{pattern}[?]	the previous line where {pattern} matches *:?*
	\/		the next line where the previously used search
			pattern matches
	\?		the previous line where the previously used search
			pattern matches
	\&		the next line where the previously used substitute
			pattern matches

    Range Examples
    
	.+3		three lines below the cursor
	/that/+1	the line below the next line containing "that"
	.,$		from current line until end of file
	0;/that		the first line containing "that", also matches in the
			first line.
	1;/that		the first line after line 1 containing "that"


    54s/Fool/Cool/g  Substitute command only on line 54
    .,+10s/Fool/Cool/g same but on the current line and the next 10 lines

    
    If you want to grab the next 5 lines type "5:" and it is replaced with
    ".,+4" the equivalent range

    Move the next 3 lines to the end of the file
    .,+2m $

### VISUAL MODE AND RANGE. 

    After making selection with visual mode enter
    :
    And then the command will use the Visual selection as its range. 
    
    :* can be used after the Visual mode has ended.


    Some commands can take a suffix count number
    example:
        s/^/#/ 5  (will add # signs to the beginning of the next 5 lines



## WINDOWN COMMANDS
    <C-w>c to close the current window
    <C-w><C-r> Rotate windows downwards
    <C-w> r  Rotate windows upwards
    <C-w><C-x> Swap windows
    <C-w> K  Change two vertical windows to two horizontal
    <C-w> H  Change two vertical windows to two vertical

    <C-w> = Make all windows equal
    <C-w> - Decrease height
    <C-w> < Decrease width
    <C-w> > Increase width
    Or use the Mouse!!









