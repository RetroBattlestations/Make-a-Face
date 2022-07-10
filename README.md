This is the program for the **twelfth** RetroBattlestations BASIC
challenge. 

This is a silly little program that lets you "make a face". The
concept is to simulate a toy which uses small blocks with different
patterns on them to let you create a face. The program doesn't use any
pixel based graphics, but can take advantage of character based
graphics such as those found on Commodore and Atari machines. It could
probably be ported to teleprinter type machines, however to make it
more interactive it currently uses cursor positioning.

For more details about the challenge, check out the post here:

  https://redd.it/vvv451

## The crazy tile encoding ##

When working with unfamiliar computers it's often difficult to figure
out how to type in characters outside of the normal ASCII printable
characters. Odd non-ASCII characters are also challenging to make
understandable or store in files on newer computers. Because of this
the choice was made to use a funky "base 64" encoding for the
tiles. The first letter is the base character in the standard
uppercase only 64 character range (32-95), and the second character is
the number of times to add 64 to the ASCII character, allowing for
encoding of up to 256 characters in two reasonably easy to type
characters. For the second character I felt that it would be better
for "A" to represent zero rather than the space character, so
numbering starts from "A" and wraps around to "@" as the highest
value.

The color information is also encoded into the second byte by
multiplying the color value by 4, allowing use of all 6 bits.

## Optional tile editor feature ##

I have included a tile editor as part of the program, but it is not
necessary to type it in if you do not plan to try to design your own
tiles. I felt that an editor would be useful for those who want to try
to port the program to a new platform, since it would allow viewing
of, and experimenting with, the crazy encoding method used by tiles in
the DATA statements.

## Porting ##

Before you start working on porting the program and changing things to
work on your machine, try running the Commodore 64 version in an
emulator (or real hardware if you are so inclined) so you can see how
the program works and what it does. The advantage of testing in an
emulator is that many emulators will allow you to easily paste text as
if it were keyboard input so you don't need to hassle with manually
typing it in or figure out how to convert the listing to a tape or
disk image.

See [List of Computers With On-Board BASIC](https://en.wikipedia.org/wiki/List_of_Computers_With_On-Board_BASIC)

## Enhancement Ideas ##

* Define a custom character set
* Add a way to rotate blocks
* Add a way to save and load faces
* Use shapes on Apple II instead of text
* Make it run faster without resorting to assembly or unreadable code
* A way to print to hardcopy

## Typing Tips ##

When typing the program in you can leave off any lines which begin
with REM, they are not needed for the program to run. On many
platforms you can leave out the whitespace between keywords and
operators. IBM BASIC is not one of those however.

*Note*: On the TRS-80 Color Computer and BBC Micro you need to include
      the spaces around any IF, AND, OR, or THEN statement.

If you make a mistake and don't want to retype the entire line, most
of the BASICs have a way to make corrections.

### Amstrad CPC (464/664/6128/464+/6128+) ###

  On Amstrad CPC, use AUTO to start typing commands. Use the arrow keys
  to move about the line. Exit the AUTO mode py pressing Escape. You can
  also start on a specific line by entering AUTO 100 (for line 100).

  To go to the start or the end of the line use CONTROL+Arrow keys. You
  can also use SHIFT+Arrow keys to use the copy cursor. This is a second
  cursor that you move independendly, and will copy whatever is under it
  to the main cursor when you press COPY.

### Apple II computers ###

  On an Apple II+ use LIST <line number> to print the line with an
  error, then use ESC followed by A/B/C/D to move the cursor one step
  at a time. Position the cursor at the beginning of the line, then
  use the right arrow to move over the line and fix the error. Be sure
  to arrow all the way to the end of the entire line before you hit
  RETURN!

  On an enhanced Apple IIe, Apple IIc, or Apple IIgs you can also use
  ESC with the arrow keys. In 80 column mode (enter with PR#3) the
  cursor will change to a white block with a + in it, push ESC to drop
  out of movement mode.

### BBC Micro ###

  Use LIST <line number> to print the line with a mistake, then use
  the arrow keys to move up to the beginning of the line. Each press
  of the copy key will type in the character under the cursor. Make
  any necessary edits by just typing on the keyboard and using copy to
  avoid retyping everything.

### Commodore 64, Plus/4, and 128 ###

  Like the others, use LIST <line number> to display the line with
  problems, then use the arrow keys to move up and make any
  corrections. By pressing shift-INST you can insert a blank character
  if you missed something. Unlike the Apple II you don't need to arrow
  to the end of the line before pushing RETURN.

### IBM Cassette BASIC, Disk BASIC, Advanced BASIC, GW-BASIC ###

  Type EDIT <line number> and it will print the line on the screen and
  put your cursor at the beginning of the line. Arrow left/right and
  you can use Insert & Delete to make corrections. Like Commodore
  BASIC, you don't need to arrow to the end of the line before pushing
  RETURN.

### TI-99/4A Extended BASIC ###

  Type the line number and then arrow up (FCTN+E) and it will enter
  edit mode with that line loaded.  You can move within the line with
  arrow left (FCTN+S) and arrow right (FCTN+D) and move to the
  previous or next line with arrow up (FCTN+E) or arrow down (FCTN+X).
  You can delete the character under the cursor with DEL (FCTN+1) or
  turn on insert mode to insert extra characters with INS (FCTN+2).
  You do not need to move to the end of the line before pressing
  ENTER.

### TRS-80 model 100 ###

  This has to be the best built-in BASIC editor I've seen so far! Just
  type EDIT and the entire BASIC program will be loaded into the
  built-in word processor where you can make any changes you
  want. Press F8 to exit the editor and go back to BASIC.

### ZX81, Timex-Sinclair 1000, and ZX Spectrum ###

  Having a hard time finding where all the BASIC keywords are hidden?
  Get [Commander le Clef's Secret Encoder
  Wheel](http://retrobattlestations.com/Cmdr-le-Clef/Secret-Encoder-Wheel.pdf)
  with an alphabetical sorted listing of keywords and the secret
  keypresses required to enter them.
