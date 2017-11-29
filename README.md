# Femto Emacs
Femto is an extended version of Atto Emacs.

> A designer knows he has achieved perfection not when there is nothing left to add, but when there is nothing left to take away.
> -- <cite>Antoine de Saint-Exupery</cite>

## Goals of Femto Emacs
* To extend Atto Emacs with filename completion, dired, buffer menu and the ability to run a shell command.
* Provide a rich level of functionality in the smallest amount of code
* Femto Emacs will eventually have it own lisp extension languauge.
* Be easy to understand without extensive study (to encourage further experimentation).

## IMPORTANT NOTE - THIS BRANCH IS NOT MAINTAINED

This branch was an intermediary project in order to seed the work done on FemtoEmacs.  As such this branch is no longer maintained and I plan to only put bug fixes into Atto or FemtoEmacs.

 https://github.com/FemtoEmacs/Femto-Emacs
 
 https://github.com/hughbarney/Femto-Emacs

## Why the name Femto?
Femto is an extended version of Atto Emacs.

In Defining Atto as the lowest functional Emacs I have had to consider the essential feature set that makes Emacs, 'Emacs'.  I have defined this point as a basic Emacs command set and key bindings; the ability to edit multiple files (buffers), and switch between them; edit the buffers in mutliple windows, cut, copy and paste; forward and reverse searching and a replace function. The proviso being that all this will fit in less than 2000 lines of C.

The small Emacs naming scheme appears to use sub-unit prefixes in decending order with each further reduction of functionality.

Atto means 10 to the power of minus 18.

An extended Atto would therefore be called Femto (10 to the power of minus 15).


## Derivation
Femto is based on the Atto codebase [0] (as of Atto 1.6)
Atto was based on the public domain code of Anthony Howe's editor (commonly known as Anthony's Editor or AE, [2]).

## Comparisons with Other Emacs Implementations

    Editor         Binary   BinSize     KLOC  Files

    femto          femto      43397     2.1k     11
    atto           atto       33002     1.9k     10
    pEmacs         pe         59465     5.7K     16
    Esatz-Emacs    ee         59050     5.7K     14
	GNOME          GNOME      55922     9.8k     13
    Zile           zile      257360    11.7k     48
    Mg             mg        585313    16.5K     50
    uEmacs/Pk      em        147546    17.5K     34
    Pico           pico      438534    24.0k     29
    Nano           nano      192008    24.8K     17
	jove           jove      248824    34.7k     94
	Qemacs         qe        379968    36.9k     59
    ue3.10         uemacs    171664    52.4K     16
    GNUEmacs       emacs   14632920   358.0k    186



## Femto Key Bindings
    C-A   begining-of-line
    C-B   backward-character
    C-D   delete-char
    C-E   end-of-line
    C-F   forward Character
    C-G	  Abort (at prompts)
    C-H   backspace
    C-I   handle-tab
    C-J   newline
    C-K   kill-to-eol
    C-L   refresh display
    C-M   Carrage Return
    C-N   next line
    C-P   previous line
    C-R   search-backwards
    C-S	  search-forwards
    C-U   Undo
    C-V   Page Down
    C-W   Kill Region (Cut)
    C-X   CTRL-X command prefix
    C-Y   Yank (Paste)

    M-<   Start of file
    M->   End of file
    M-v   Page Up
    M-f   Forward Word
    M-b   Backwards Word
    M-g   goto-line
    M-r   Search and Replace
    M-w   copy-region

    C-<spacebar> Set mark at current position.

    ^X^B  List Buffers
    ^X^C  Exit. Any unsaved files will require confirmation.
    ^X^F  Find file; read into a new buffer created from filename.
    ^X^S  Save current buffer to disk, using the buffer's filename as the name of
    ^X^W  Write current buffer to disk. Type in a new filename at the prompt to
	^X@   shell-command (you are prompted for a command which is sent to the shell
	      and the result is displayed in the *output* buffer
    ^Xi   Insert file at point
    ^X=   Show Character at position
    ^X^N  next-buffer
    ^Xn   next-buffer
    ^Xk   kill-buffer
    ^X1   delete-other-windows
    ^X2   split-window
    ^Xo   other-window

    Home  Beginning-of-line
    End   End-of-line
    Del   Delete character under cursor
	Ins   Toggle Overwrite Mode
    Left  Move left
    Right Move point right
    Up    Move to the previous line
    Down  Move to the next line
    Backspace delete caharacter on the left
    Ctrl+Up      beginning of file
    Ctrl+Down    end of file
    Ctrk+Left    Page Down
    Ctrl+Right   Page Up

### Copying and moving
    C-<spacebar> Set mark at current position
    ^W   Delete region
    ^Y   Yank back kill buffer at cursor
    M-w  Copy Region

A region is defined as the area between this mark and the current cursor position. The kill buffer is the text which has been most recently deleted or copied.

Generally, the procedure for copying or moving text is:
1. Mark out region using M-<spacebar> at the beginning and move the cursor to the end.
2. Delete it (with ^W) or copy it (with M-W) into the kill buffer.
3. Move the cursor to the desired location and yank it back (with ^Y).

### Searching
    C-S or C-R enters the search prompt, where you type the search string
    BACKSPACE - will reduce the search string, any other character will extend it
    C-S at the search prompt will search forward, will wrap at end of the buffer
    C-R at the search prompt will search backwards, will wrap at start of the buffer
    ESC will escape from the search prompt and return to the point of the match
    C-G abort the search and return to point before the search started

## Building on Ubuntu (using UTF8 support in ncurse / ncursesw)

When building on Ubuntu you will need to install the libcurses dev package.
NOTE: As of Femto 1.2 you will also need the libncursesw (wide) library

$ sudo apt-get install apt-file
$ apt-file update

now search for which package would have curses.h
$ apt-file search curses.h

libncurses5-dev: /usr/include/curses.h

$ sudo apt-get install libncurses5-dev libncursesw5-dev


## Future Enhancements

The following enhancements are envisaged.
* A buffer menu facility
* Directory and file manegement (Dired) functionality.
* A Lisp or Scheme based extension languauge.

## Known Issues
	Goto-line will fail to go to the very last line.  This is a special case that could easily be fixed.

## Copying
  Femto code is released to the public domain.
  hughbarney@gmail.com November 2017

## References
    [0] Atto Emacs - https://github.com/hughbarney/atto
    [1] Perfect Emacs - https://github.com/hughbarney/pEmacs
    [2] Anthony's Editor - https://github.com/hughbarney/Anthony-s-Editor
    [3] MG - https://github.com/rzalamena/mg
    [4] Jonathan Payne, Buffer-Gap: http://ned.rubyforge.org/doc/buffer-gap.txt
    [5] Anthony Howe,  http://ned.rubyforge.org/doc/editor-101.txt
    [6] Anthony Howe, http://ned.rubyforge.org/doc/editor-102.txt

