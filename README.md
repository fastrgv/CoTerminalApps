![screenshot](https://github.com/fastrgv/CoTerminalApps/blob/master/crush.jpg)

# CoTerminalApps
Retro Games that run in a color-capable terminal on any platform with GNAT GPL installed.

Grab the file Cotapps.tar.gz under "release...latest" for all source and data, or try this link:

https://github.com/fastrgv/CoTerminalApps/releases/download/v1.1.0/cot5jan17.tar.gz


# CoTerminalApps v 1.1.0

## What's new:

**ver 1.1.0 -- 5jan17**

* Now supply prebuilt binaries for OS-X and Linux.  Look in ./bin/gnu or ./bin/osx/.
* Improved build system.



**ver 1.0.7 -- 22aug16**

* added two sokoban solvers (puller.adb, ibox.adb).
* added cslid solver (bfs.adb).
* added crush solver (bfsr.adb)
* improved pacman gameplay, collision-detection, randomization.


**ver 1.0.6 -- 27jul16**

* added CoTerminal-DirtyDozen block slider (cdd.adb)
* added CoTerminal-Nine by Grabarchuk (c9.adb)
* improvements in csok::Draw that include speedup option (s-key).
* added restart option to cslid.adb, crush.adb
* added CoTerminal-Pacman (cpac.adb)


**ver 1.0.5 -- 16jul16**

* added HoleInOne, HoleInOne+4 (chio.adb, chio4.adb)
* small improvement to sokoban key response.


**ver 1.0.4 -- 11jul16**

* fixed logic error in CoTerminalRush (crush.adb).


**ver 1.0.3 -- 5jul16**

* added csok game.


**ver 1.0.2 -- 4jul16**

* Added caz, c7 puzzle games.


**ver 1.0.1 -- 3jul16**

* Added block slider game named "cslid".
* Greater care taken to ignore key escape codes.


**ver 1.0.0 -- 28jun16**

* original release.


===============================================================
## Introduction
CoTerminalApps contains color-terminal puzzle games that can run on any OS capable of installing the GNAT GPL Ada compiler.

There are 10 apps that use ascii characters only:  crush, cslid, c7, caz, csok, chio, chio4, c9, cdd, cpac


Usable keys for all:

* arrow-keys for movement;
* (q)=quit
* (?)=help toggle


===========================================================================

### CoTerminal-pacman (cpac.adb)
A minimalist version of Pacman with 9 predefined levels.  Playable now, with further improvements expected.


### CoTerminal-Rush (crush.adb)
Colored, non-graphical Traffic-Rush puzzle game designed to run in a terminal window.

Horizontal and vertical strings of letters represent cars and trucks in a crowded parking garage.  The objective is to move them around lengthwise in order to be able to get red car "a" to the exit, which is either at the right or top of the garage.  Note that the last digits in each puzzle name represents the minimum number of moves to win.

Also, a solver named bfsr has been added that works for puzzle files with the ".rush" filename extension.  The command line is "bfsr puzzle-file-name".  Compile it with the command "cmp.sh bfsr".


### CoTerminal-BlockSlide (cslid.adb), CoTerminal-DirtyDozen (cdd.adb)
Colored, non-graphical Block Slider puzzle games designed to run in a terminal window.

Colored blocks of letters can be moved horizontally or vertically wherever there is space.  The objective is to move the red block to a specified goal position.

Also, a solver named bfs has been added that works for puzzle files with the ".blok" filename extension.  The command line is "bfs puzzle-file-name".  Compile it with the command "cmp.sh bfs".


### Gameplay: crush, cslid

"?" toggles the help screen.  The "+" and "-" keys (next, previous) are used to cycle through the large number of predefined puzzles.  You can reset a puzzle by typing "+" then "-".

First, one selects a vehicle or block by typing its identifier letter.  Then use the arrow keys to move it.  Note that manual selection is not always necessary, as there is an auto-select mechanism for those times when only one selection may move in a given direction.  


===============================================================
### CoTerminal Seven, A2Z (c7.adb, caz.adb)

c7 is a flat representation of a 2x2x2 cube with one missing that allows sliding permutations.  Here, the 8-1 elements are labelled 1..7.

caz is a flat representation of a 3x3x3 cube with one missing that allows sliding permutations.  The 27-1 elements are conveniently labelled with the english alphabet.

Both the "caz" and "c7" puzzles work the same:

* note the original order, and blank location;
* mix;
* then restore.

A character in an adjacent row, column, or layer may be moved to the empty space using the keyboard.

Pressing the (home) key on a typical keyboard produces the character 'H'.  So assuming that (home)=>'H', (end)=>'F', (up)=>'A', etc...
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

### CoTerminal-sokoban (csok.adb)
Move the pusher >< with the arrow keys in order to push all the boxes [] onto the goals :: in which case they look like {}.  Various other functions available on the help screen.  Includes a very large family of puzzle files.

Two sokoban solvers named puller & ibox have been added.  The command line is "solver-name puzzle-file-name max-levels level-number".  Note that the max-levels are embedded into each puzzle file name.

The output file (named similarly to the input file) contains directions from the set {u,d,l,r,U,D,L,R}, where upper case indicates a push.  It is size-limited to 17 or fewer boxes, and 128 or fewer interior puzzle positions.  Compile it with the command "cmp.sh puller" or "cmp.sh ibox".

There are many cases these solvers cannot handle, but they are pretty good at sovling certain types of puzzles, particularly the more dense ones.


### CoTerminal-HoleInOne (chio.adb, chio4.adb)
Move the red 2x2 'a' block into the center of the four L-shaped corner pieces.

### CoTerminal-Nine (c9.adb)
Reverse the order of the numbered blocks.

===============================================================
## Build Instructions (tested on Linux and OSX):
* Manually install GNAT GPL 2016 from libre.adacore.com/download/
* Insure gnatmake is in searchpath. (echo $PATH).
* Note that ~/libs/gnu/ and ~/libs/osx/ directories have already been populated with libgnatcoll.so.2016 libraries.  It is claimed that these must match the version of gnat being used.
* Compile by typing "ocmp.sh [game]" for OSX, or "lcmp.sh [game]" for linux, to create a command-line executable, where [game] is in the set {crush,cslid,caz,c7,csok,chio,chio4,c9,cdd,cpac}.  These scripts streamline the build process by allowing auxilliary libraries and files to be neatly hidden in subdirectories.


## Preparing GnatColl Libraries -- (done already for OS-X, Linux)
* Download GNATCOLL from libre.adacore.com/download/
* Build gnatcoll, but do not install.  Even if errors occur, the one library we need may have been correctly generated.  Under ~/src/lib/gnatcoll/relocatable/ you will find newly generated library files with names beginning with "libgnatcoll".  Copy them into ~/libs/SYS/, where SYS is one of {gnu,osx,win}.  Try to preserve the softlinks.
* Copy gnatcoll.ads, gnatcoll-terminal.ads, gnatcoll-terminal.adb into ~/adainclude/ if they are any different from the ones there already.
* On MSWindows, a working script named "wcmp.sh" has yet to be built,
	but should be somewhat similar to "lcmp.sh".

===============================================================
## Running:
Your terminal must accept the "clear" command, and must be 50 chars wide by 20 lines (57x35 for pacman).  Simply type the executable name to begin.


===============================================================
## Known Problems:
Occasionally, there is poor key response.  This might be due to the many color changes with each draw.  If this happens, hit the s-key to toggle alternate colors that redraw much faster.

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


----------------------------------------------
## Other Credits and Thanks:
Serhiy Grabarchuk and Peter Grabarchuk for their "Hole in One", "Hole in One plus 4", and "Nine" puzzles.

Mike Billars [michael@gmail.com] for his C-version of Pacman for the console, after which this Ada version was modelled (gnu gpl).

----------------------------------------------
## Best Download Site for all my games:
https://github.com/fastrgv?tab=repositories
