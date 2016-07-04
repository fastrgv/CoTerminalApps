# CoTerminalApps
Retro Games that run in a color-capable terminal on any platform.

Grab the file coterm*.tar.gz under "release...latest" for all source and data.



# CoTerminalApps v 1.0.2

## What's new:

**ver 1.0.2 -- 4jul16**

* Added a2z, seven puzzle games.


**ver 1.0.1 -- 3jul16**

* Added block slider game named "bslid".

===============================================================
## Introduction
CoTerminalApps contains color-terminal puzzle games that can run on any OS capable of installing the GNAT GPL Ada compiler.

There are four apps:  

* CoTerminalRush (crush.adb) 
* BlockSlider (bslid.adb)
* seven (seven.adb)
* a2z (a2z.adb)

...described below.

Usable keys:

* arrow-keys for movement;
* (q)=quit
* (?)=help toggle


=============================================================================
### CoTerminalRush
Colored, non-graphical Traffic-Rush puzzle game designed to run in a terminal window.

Horizontal and vertical strings of letters represent cars and trucks in a crowded parking garage.  The objective is to move them around lengthwise in order to be able to get red car "a" to the exit, which is either at the right or top of the garage.  Note that the last digits in each puzzle name represents the minimum number of moves to win.

### BlockSlide
Colored, non-graphical Block Slider puzzle game designed to run in a terminal window.

Colored blocks of letters can be moved horizontally or vertically wherever there is space.  The objective is to move the red block to a specified goal position.

### Gameplay: crush, bslid

"?" toggles the help screen.  The "+" and "-" keys (next, previous) are used to cycle through the large number of predefined puzzles.  You can reset a puzzle by typing "+" then "-".

First, one selects a vehicle or block by typing its identifier letter.  Then use the arrow keys to move it.  Note that manual selection is not always necessary, as there is an auto-select mechanism for those times when only one selection may move in a given direction.  


===============================================================
### seven, a2z

seven is a flat representation of a 2x2x2 cube with one missing that allows sliding permutations.  Here, the 8-1 elements are labelled 1..7.

a2z is a flat representation of a 3x3x3 cube with one missing that allows sliding permutations.  The 27-1 elements are conveniently labelled with the english alphabet.

Both the "a2z" and "seven" puzzles work the same:

* note the original order, and blank location;
* mix;
* then restore.

A character in an adjacent row, column, or layer may be moved to the empty space using the keyboard.

Typically, the (home) key produces the character 'H'.  So assuming that (home)=>'H', (end)=>'F', (up)=>'A', etc...
the key mapping follows:

* (1)..(5): mix;  higher values are more difficult.

* (up),(i): north
* (dn),(k): south
* (rt),(l): east
* (lt),(j): west
* (home),(\),(u),(.),(-): layer-up
* (end),(/),(o),(+): layer-dn

* (?): help
* (q): quit


===============================================================
## Build Instructions (tested on Linux and OSX):
* Manually install GNAT GPL 2016 from libre.adacore.com/download/
* Insure gnatmake is in searchpath. (echo $PATH).
* Note that ~/libs/gnu/ and ~/libs/osx/ directories have already been populated with libgnatcoll.so.2016 libraries.  It is claimed that these must match the version of gnat being used.
* Compile crush by typing "ocmp.sh [game]" for OSX, or "lcmp.sh [game]" for linux, to create a command-line executable, where [game] represents "crush", "bslid", "a2z", or "seven".  These scripts streamline the build process by allowing auxilliary libraries and files to be neatly hidden in subdirectories.


## Preparing GnatColl Libraries -- (done already for OS-X, Linux)
* Download GNATCOLL from libre.adacore.com/download/
* Build gnatcoll, but do not install.  Even if errors occur, the one library we need may have been correctly generated.  Under ~/src/lib/gnatcoll/relocatable/ you will find newly generated library files with names beginning with "libgnatcoll".  Copy them into ~/libs/SYS/, where SYS is one of {gnu,osx,win}.  Try to preserve the softlinks.
* Copy gnatcoll.ads, gnatcoll-terminal.ads, gnatcoll-terminal.adb into ~/adainclude/ if they are any different from the ones there already.
* On MSWindows, a working script named "wcmp.sh" has yet to be built,
	but should be somewhat similar to "lcmp.sh".

===============================================================
## Running:
Open a terminal and type the executable name to begin.

===============================================================
## Legal Mumbo Jumbo:

CoTerminalApps is covered by the GNU GPL v3 as indicated in the sources:

 Copyright (C) 2016  <fastrgv@gmail.com>

 This program is free software: you can redistribute it and/or modify
 it under the terms of the GNU General Public License as published by
 the Free Software Foundation, either version 3 of the License, or
 (at your option) any later version.

 This program is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 GNU General Public License for more details.

 You may read the full text of the GNU General Public License
 at <http://www.gnu.org/licenses/>.
