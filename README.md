# CoTerminalApps
Retro Games that run in a color-capable terminal, and on any platform.

Grab the file coterm30jun16.tar.gz under "release" for all source and data.



# CoTerminalApps v 1.0.1

## What's new:


**ver 1.0.1 -- 30jun16**

* Added block slider game named "bslid".


**ver 1.0.0 -- 28jun16**

* original release.


===============================================================
## Introduction
CoTerminalApps contains color-terminal puzzle games that can run on any OS capable of installing the GNAT GPL Ada compiler.

There are currently two apps:  

* CoTerminalRush (crush.adb) 
* BlockSlider (bslid.adb)

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

### Gameplay:

"?" toggles the help screen.  The "+" and "-" keys (next, previous) are used to cycle through the large number of predefined puzzles.  You can reset a puzzle by typing "+" then "-".

First, one selects a vehicle or block by typing its identifier letter.  Then use the arrow keys to move it.  Note that manual selection is not always necessary, as there is an auto-select mechanism for those times when only one selection may move in a given direction.  

===============================================================
## Build Instructions (Linux and OSX):
* Manually install GNAT GPL 2016 from libre.adacore.com/download/
* Insure gnatmake is in searchpath. (echo $PATH).
* Note that ~/libs/gnu/ and ~/libs/osx/ directories have already been populated with libgnatcoll.so.2016 libraries.  It is claimed that these must match the version of gnat being used.
* Compile crush by typing "ocmp.sh [game]" for OSX, or "lcmp.sh [game]" for linux, to create a command-line executable, where [game] represents either "crush" or "bslid".  These scripts streamline the build process by allowing auxilliary libraries and files to be neatly hidden in subdirectories.


## Preparing GnatColl Libraries -- (done already for OS-X, Linux)
* Download GNATCOLL from libre.adacore.com/download/
* Build gnatcoll, but do not install.  Even if errors occur, the one library we need may have been correctly generated.  Under ~/src/lib/gnatcoll/relocatable/ you will find newly generated library files with names beginning with "libgnatcoll".  Copy them into ~/libs/SYS/, where SYS is one of {gnu,osx,win}.  Try to preserve the softlinks.
* Copy gnatcoll.ads, gnatcoll-terminal.ads, gnatcoll-terminal.adb into ~/adainclude/ if they are any different from the ones there already.
* On MSWindows, a working script named "wcmp.sh" has yet to be built,
	but should be somewhat similar to "lcmp.sh".

===============================================================
## Running:
Open a terminal and type "crush" or "bslid" to begin.

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


