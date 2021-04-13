![screenshot](https://github.com/fastrgv/CoTerminalApps/blob/master/crush.jpg)

![screenshot](https://github.com/fastrgv/CoTerminalApps/blob/master/puzzles.png)

# CoTerminalApps
Retro Ascii Character Games that run in a color-capable terminal on Windows, OSX, & Linux.

Grab the large file under "release...latest" for all source and data, or try this link:

https://github.com/fastrgv/CoTerminalApps/releases/download/v2.2.3/co10mar21.7z

then type "7z x filename.7z" to extract the archive.

#### Note to github downloaders: Please ignore the "Source code" zip & tar.gz files. (They are auto-generated by GitHub). Click on the large 7z file under releases to download all source & binaries (Windows,Mac & Linux). Then, type "7z x filename" to extract the archive. 








# CoTerminalApps with OpenAL Sound

## What is new:

**ver 2.2.3 -- 10mar21**
* c7,c9,caz now have solvers & improved screens.
* c7,caz now allow restart using (r)-key.
* nexus/puzzles.txt now limited to 60 columns.


**ver 2.2.2 -- 06mar21**
* Csok now has alternate character set toggled with (c)-key.
* Csok now has 3 embedded autosolvers.


**ver 2.2.1 -- 21feb21**
* Updated sokoban autosolvers & csok.
* Added more capable hbox4 sokoban solver.
* Improved build scripts.

**ver 2.2.0 -- 8nov20**
* Completely revised & enhanced sound system; 
* Using cross-platform OpenAL binding;
* Simplified build process & coding;
* Pacman background music now restored.




===============================================================
## Introduction

CoTerminalApps is a portable collection of non-graphical, colored-ascii-character puzzles & games that run in a commandline terminal on Windows, OS-X and Gnu/Linux. Now with sound.

Has runtime-priority control of console terminal, if needed.

Rebuildable using the free AdaCore GNAT Ada compiler.  

Includes rpn(calculator), cpac(Pacman), cfrog(Frogger) and 10 puzzle games that use ascii characters only:  crush(rush-hour), cslid(klotski), c7(flat7), caz(flatAZ), csok(sokoban), chio(hole-in-one), chio4(hole-in-one+4), c9(nine), cdd(dirty-dozen), cpan(panama);

See a visual of the 10 puzzles in the image "./puzzles.png".


Usable keys for all:

* arrow-keys or WASD or IJKL for movement;
* (q)=quit
* (?)=help toggle
* 
All puzzles & games can be called directly from the command line; e.g.

* bin\win\cpac.exe

but it is more convenient to use the 3 selector apps.

All puzzles & games can now be launched from the selector app thusly:

On Windows type "winterm.bat"

On Mac/OSX type "macterm.sh"

On Linux type "gnuterm.sh"

Then use the keyboard arrow keys to highlight the desired game, and hit (enter)-key.


### For Maximal Enjoyment...
Keyboard setup is important.  You should have a short key-delay and fast repeat rate setting. 

Screen setup is important, too. It is recommended to resize your terminal window to 60 chars. wide by XX lines tall; then enlarge the font until the window just barely fits your computer screen. For Pacman: XX=40, all others: XX=25 is sufficient.


===========================================================================


### CoTerminal-Rush (crush.adb)
Colored, non-graphical Traffic-Rush puzzle game designed to run in a terminal window.

Horizontal and vertical strings of letters represent cars and trucks in a crowded parking garage.  The objective is to move them around lengthwise in order to be able to get red car "a" to the exit, which is either at the right or top of the garage.  Note that the last digits in each puzzle name represents the minimum number of moves to win.

A stand alone autosolver, bfsr, is provided, but now, an autosolver is embedded into this game.  At any time you may press the (=)-key to begin stepping toward a solution.


### CoTerminal-BlockSlide (cslid.adb), CoTerminal-DirtyDozen (cdd.adb)
Colored, non-graphical Block Slider puzzle games designed to run in a terminal window.

Colored blocks of letters can be moved horizontally or vertically wherever there is space.  The objective is to move the red block to a specified goal position.

A stand alone autosolver, bfsl, is provided, but now, an autosolver is embedded into these games.  At any time you may press the (=)-key to begin stepping toward a solution.


### Gameplay: crush, cslid

"?" toggles the help screen.  The "+" and "-" keys (next, previous) are used to cycle through the large number of predefined puzzles.  You can reset a puzzle by typing "r". You can autosolve by typing "=".

First, one selects a vehicle or block by typing its identifier letter.  Then use the arrow keys to move it.  Note that manual selection is not always necessary, as there is an auto-select mechanism for those times when only one selection may move in a given direction.  


===============================================================
### Seven, A2Z (c7.adb, caz.adb)

c7 is a flat representation of a 3D 2x2x2 cube with one cubelet missing that allows sliding permutations.  Here, the elements are labelled 1..7.

caz is a flat representation of a 3x3x3 cube with one cubelet missing that allows sliding permutations.  The elements are labelled with the english alphabet.

Both the "caz" and "c7" puzzles work the same:

* note the original order, and blank location;
* mix;
* then restore.

A character in an adjacent row, column, or layer may be moved to the empty space using the keyboard.

Pressing the (home) key on a typical keyboard produces the character 'H'.  So assuming that (home)=>'H', (end)=>'F', (up)=>'A', etc...
the key mapping follows:

* (1)..(5): mix;  higher values are more difficult.

* (up),(i),(w): north
* (dn),(k),(s): south
* (rt),(l),(d): east
* (lt),(j),(a): west
* (home),(\),(u),(.),(-): layer-up
* (end),(/),(o),(+): layer-dn

* (?): help
* (q): quit



===============================================================

### CoTerminal-sokoban (csok.adb)
Move the pusher >< with the arrow keys in order to push all the boxes [] onto the goals :: in which case they look like {}.  Various other functions available on the help screen.  Includes a very large family of puzzle files.

Three [external] sokoban solvers named iplr3r, ibox3r & hbox4 are available.  The command line is "solver-name puzzle-file-name max-levels level-number".  Note that the max-levels are embedded into each puzzle file name. The solvers print solution-strings to the terminal screen.

There are many cases the first two solvers cannot handle, but they are pretty good at solving smaller puzzles, particularly the more dense ones. Hbox4 is the most capable.

Two time-limited solvers are embedded into csok.  At any time you may press the (=)-key to see if the solver #1 can help you.  If so, you will be prompted to keep pressing that same key to proceed toward a solution.  No prompt means either the present state is unsolvable, or merely that the embedded algorithm failed.  Similarly, the (.)-key initiates solver #2. These can give you a headstart toward a correct solution by limited use of this feature.  Once you think you can solve it yourself, stop using the solver and proceed manually.  This really helps when you cannot see what your next move should be.

Finally, an optional single command-line argument (decimal float) specifies a timeout interval to wait for the internal autosolver before giving up.  The default is 10.0 seconds.

### CoTerminal-HoleInOne (chio.adb, chio4.adb)
Move the red 2x2 'a' block into the center of the four L-shaped corner pieces.

### CoTerminal-Nine (c9.adb)
Reverse the order of the numbered blocks.

### RPN (reverse polish notation) command line calculator
A cult classic.  Recalls the HP rpn functionality. This version uses differentials to calculate an error estimate.

### Pacman (cpac)
Pacman, is a kid friendly ascii character version of Pacman that plays in a commandline terminal.  Pure minimalism with classic sounds and 9 predefined levels.  

Now with runtime-priority control to prevent terminal freezes on Windows, plus commandline control of gamespeed & ghostspeed.

Runs on Windows, OSX & Linux.

Keyboard setup is important.  You should have a short key-delay and fast repeat setting.  

The arrow keys, or wasd-keys, or ijkl-keys control movement.  The (x),(q) keys quit;  (p) pauses game.

Includes executables and source code.  Note that this game does NOT require an ncurses library in your environment.

cpac can be given 2 optional command line parameters:
	.) game speed 0..9; 0=slow, 5=default=medium, 9=fast;
	.) ghost speed 0..9; 0=stopped, 2=default=easy, 9=fast.
If you want to try non-default values for these params, you need to run directly from the directory of the executable. To do this: "cd bin/gnu" or "cd bin/osx" or "cd bin\win", first.

Before running cpac, it is recommended to resize your terminal to 60 chars. wide by 40 lines tall; then, perhaps, enlarge the font.



### Frogger (cfrog)
Terminal frogger is a kid friendly ascii character version of Frogger that plays in a commandline terminal.  Pure minimalism with classic sounds and three levels.

@@@@ is a raft of lillypads, 
QQQQ is a team of turtles, 
==== is a log, 
TTT is a truck, 
ccc is a car.

Runs on Windows, OSX & Linux.

Keyboard setup is important.  You should have a short key-delay and fast repeat setting.  

The arrow keys, or wasd-keys, or ijkl-keys control movement.  The (x),(q) keys quit.

Before running cfrog, it is recommended to resize your terminal to 56 chars. wide by 21 lines tall; then, perhaps, enlarge the font.



===============================================================
## Setup & Running:

Mac users see "osx-setup.txt".
Windows users see "windows-setup.txt".

Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this. The proper command to extract the archive and maintain the directory structure is "7z x filename".

Open a commandline terminal, and cd to the install directory.

Ensure your keyboard has a short key-delay and fast repeat.

Minimize the size of your terminal window.  Your terminal must be 60 chars wide by 40 lines for pacman, smaller for others.  

Enlarge the Font so that the window fills your monitor.

To launch the game selector App, depending on your system, type:

winterm.bat

or
macterm.sh

or
gnuterm.sh

Note that any individual app may still be executed from the directory appropriate to your O.S.  For example, on Windows you can CD to bin\win and then type "cfrog" to run Frogger.

### linux caveat
The prebuilt linux executables require glibc v2.14 or newer.  That means if your distribution is older, it might not run, and you would need to rebuild.

### OSX caveat
The prebuilt OSX executables require version 10.13 (sep2017) or newer.

===========================================================================
## Compiler Scripts
There are three scripts, wbuildall.bat for Windows, lbuildall.sh for Linux, and obuildall.sh for OS-X.  They differ in where the executables are put.  Now with so many different precompiled binaries for each OS, there would be too much clutter if they were all put into the same place.


===============================================================
## Build Instructions:
Remember that prebuilt executables are already included. But, if you want to rebuild...

Manually install GNAT GPL from libre.adacore.com/download/.  If you don't like my key-mappings, edit the code as you like.

Next, edit the scripts wcmp.bat or lcmp.sh or ocmp.sh so that the path to gnatmake is correct.  These scripts streamline the build process by allowing auxilliary files to be neatly hidden in subdirectories.  And make sure it is executable.

Then type "[wlo]buildall" to create new command-line executables for your system. ( w for Windows, l for Linux, o for OSX). Note that on OSX, you must have the Apple-Xcode g++ compiler present in order to rebuild.


===============================================================

## What is special about this project?...freedom...
* uses the Ada programming language & GNAT GPL;
* runs on Macs running OSX, or PCs running Windows or Linux;
* uses only free open source software [F.O.S.S] tools & libraries;
* portable, transparent code, easy to modify, rebuild;
* uses a cross-platform implementation of OpenAL-Audio for sounds;
* pure minimalism:  no graphics, just colored ASCII characters, keyboard, & sound;




===============================================================
## License:

CoTerminalApps is covered by the GNU GPL v3 as indicated in the sources:

 Copyright (C) 2021  <fastrgv@gmail.com>

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
### SoundFiles [x.wav]
Fanfare/Applause sounds are from freesound.org and are covered by the Creative Commons Attribution noncommercial license documented in the accompanying file creativeCommons.txt. Others from 
* classicgaming.cc/classics/pac-man/sounds
* classicgaming.cc/classics/frogger/sounds
(also CreativeCommons).


----------------------------------------------
## Best Download Site for all my games:
https://github.com/fastrgv?tab=repositories

## Video BlockSlider Autosolve:
https://youtu.be/dD3VGbXv3ng

--------------------------------------------------
## Some Earlier Revision History:

**ver 2.1.0 -- 26oct20**
* Improved UI for RPN-calc.


**ver 2.0.4 -- 22sep20**
* Game-launcher now allows (return)-key to select, uses improved colors.

**ver 2.0.3 -- 23jun20**
* All apps are now launched using a single command.



