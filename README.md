![screenshot](https://github.com/fastrgv/CoTerminalApps/blob/master/crush.jpg)

# CoTerminalApps
Retro Ascii Character Games that run in a color-capable terminal on Windows, OSX, & Linux.

Grab the large file under "release...latest" for all source and data, or try this link:

https://github.com/fastrgv/CoTerminalApps/releases/download/v1.2.4/co31aug19.7z




# CoTerminalApps

## What's new:

**ver 1.2.4 -- 31aug19**

* Refined redraws for speed & correctness;  minimized cls.

**ver 1.2.2 -- 24aug19**

* Improved sokoban autosolvers (csok);
* Fixed slow key response in Windows;


**ver 1.2.1 -- 20aug19**

* Improved csok autosolver;  and enabled a second method;
* Added optional csok parameter to set default autosolve timeout;
* Updated RPN calculators to include error estimates;
* Corrected behavior in csok,cdd,crush,cslid;


**ver 1.2.0 -- 29dec18**

* Now request only high-priority rather than realtime-priority on Windows;
* Now deliver 7z archives for better compression and simplicity of extraction on all 3 platforms.


===============================================================
## Introduction

CoTerminalApps contains colored-ascii-character games that run in a commandline terminal on msWindows, OS-X and Gnu/Linux.

Now with runtime-priority control of console terminal, if needed.

They can also be rebuilt after installing the GNAT GPL Ada compiler.  

The only difference from TerminalApps is the use of the gnat library gnatcoll to enable colored characters, which makes many games/puzzles easier to understand.

Includes rpn(calculator), cpac(Pacman) and 9 puzzle games that use ascii characters only:  crush(rush-hour), cslid(klotski), c7(flat7), caz(flatAZ), csok(sokoban), chio(hole-in-one), chio4(hole-in-one+4), c9(nine), cdd(dirty-dozen), cpac(Pacman)

Keyboard setup is important.  You should have a short key-delay and fast repeat rate setting.  

Usable keys for all:

* arrow-keys or WASD or IJKL for movement;
* (q)=quit
* (?)=help toggle

Windows games are all located in .\bin\win\;
Mac games are in ./bin/osx/;
Linux games are in ./bin/gnu/;

For example, to play rush-hour on a Mac you would type:
bin/osx/crush
or else cd to ./bin/osx/ then type
crush

===========================================================================

### CoTerminal-pacman (cpac.adb)

A primitive, silent version of Pacman with 9 predefined levels.

For this game, keyboard setup is critical to playability.  One must have a short key-delay and fast repeat setting.  The arrow keys, or wasd-keys, or ijkl-keys control movement.  The (x),(q) keys quit;  (p) pauses game.

Executable can now be given 2 optional command line parameters:
	* Game Speed 0..9;  0=slow, 5=default=medium, 9=fast;
	* Ghost Speed 0..9;  0=stopped, 2=default=easy, 9=fast

So on windows, the command:
"bin\win\cpac 5 2" 
gives default settings, same as giving no parameters:
"bin\win\cpac" 



### CoTerminal-Rush (crush.adb)
Colored, non-graphical Traffic-Rush puzzle game designed to run in a terminal window.

Horizontal and vertical strings of letters represent cars and trucks in a crowded parking garage.  The objective is to move them around lengthwise in order to be able to get red car "a" to the exit, which is either at the right or top of the garage.  Note that the last digits in each puzzle name represents the minimum number of moves to win.

A stand alone autosolver, bfsr, is provided, but now, an autosolver is embedded into this game.  At any time you may press the (=)-key to begin stepping toward a solution.


### CoTerminal-BlockSlide (cslid.adb), CoTerminal-DirtyDozen (cdd.adb)
Colored, non-graphical Block Slider puzzle games designed to run in a terminal window.

Colored blocks of letters can be moved horizontally or vertically wherever there is space.  The objective is to move the red block to a specified goal position.

A stand alone autosolver, bfsl, is provided, but now, an autosolver is embedded into these games.  At any time you may press the (=)-key to begin stepping toward a solution.


### Gameplay: crush, cslid

"?" toggles the help screen.  The "+" and "-" keys (next, previous) are used to cycle through the large number of predefined puzzles.  You can reset a puzzle by typing "+" then "-".

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

Two [external] sokoban solvers named iplr3r & ibox3r have been added.  The command line is "solver-name puzzle-file-name max-levels level-number".  Note that the max-levels are embedded into each puzzle file name.

The output file (named similarly to the input file) contains directions from the set {u,d,l,r,U,D,L,R}, where upper case indicates a push.  It is size-limited to 17 or fewer boxes, and 128 or fewer interior puzzle positions.  Compile it with the command "cmp.sh iplr3r" or "cmp.sh ibox3r".

There are many cases these solvers cannot handle, but they are pretty good at sovling smaller puzzles, particularly the more dense ones.

Two time-limited solvers are embedded into csok.  At any time you may press the (=)-key to see if the solver #1 can help you.  If so, you will be prompted to keep pressing that same key to proceed toward a solution.  No prompt means either the present state is unsolvable, or merely that the embedded algorithm failed.  Similarly, the (.)-key initiates solver #2.

Finally, an optional single command-line argument (decimal float) specifies a timeout interval to wait for the internal autosolver before giving up.  The default is 10.0 seconds.

### CoTerminal-HoleInOne (chio.adb, chio4.adb)
Move the red 2x2 'a' block into the center of the four L-shaped corner pieces.

### CoTerminal-Nine (c9.adb)
Reverse the order of the numbered blocks.

### RPN (reverse polish notation) command line calculator
A cult classic.  Recalls the HP rpn functionality.  Type "rpn".  This version uses differentials to calculate an error estimate.



===============================================================
## Setup & Running:


Mac users see "osx-setup.txt".
Windows users see "windows-setup.txt".

Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this.


Ensure your keyboard has a short key-delay and fast repeat.

Minimize the size of your terminal window.  Your terminal must be 50 chars wide by 20 lines (57x35 for pacman).  

Enlarge the Font so that the window fills your monitor.

On OSX or Linux, you can type "hipr.sh" to elevate the runtime priority of all terminal applications prior to runtime.

Similary, on Windows you can CD to .\bin\win\ then run "hipri.bat". 

Then, simply type the executable name to begin.  

For example, on OSX, you would open a terminal, and cd to the install directory and type:  ./bin/osx/csok   to run the Sokoban game.  You could also cd to the executable directory ./bin/osx/ then type:  csok.



===========================================================================
## Compiler Scripts
There are three scripts, wbuildall.bat for msWindows, lbuildall.sh for Linux, and obuildall.sh for OS-X.  They differ in where the executables are put.  Now with so many different precompiled binaries for each OS, there would be too much clutter if they were all put into the same place.


===============================================================
## Build Instructions:
Remember that prebuilt executables are already included.  If you want to rebuild...

Manually install GNAT GPL from libre.adacore.com/download/.  If you don't like my key-mappings, edit the code as you like.

Next, edit the scripts wcmp.bat or lcmp.sh or ocmp.sh so that the path to gnatmake is correct.  These scripts streamline the build process by allowing auxilliary files to be neatly hidden in subdirectories.  And make sure it is executable.

Then type "[wlo]buildall" to create new command-line executables for your system.


===============================================================
## What is special about this project?
* portability, transparency, and open source freedom;
* uses GNAT GPL;
* for developers, the Ada code is easy to understand;
* essentially no graphics, and no user interface;




===============================================================
## Legal Mumbo Jumbo:

CoTerminalApps is covered by the GNU GPL v3 as indicated in the sources:

 Copyright (C) 2017  <fastrgv@gmail.com>

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

## Video BlockSlider Autosolve:
https://youtu.be/dD3VGbXv3ng

--------------------------------------------------
## Earlier Revision History:

**ver 1.1.9 -- 30nov18**

* Significant improvement to keyboard response for MsWin by setting realtime mode programmatically.


**ver 1.1.8 -- 25nov18**

* Improved csok autosolver;
* Improved autosolvers for crush, cslid, cdd.
* Corrected error in autoselect logic;


**ver 1.1.7 -- 13aug18**

* Fixed csok to handle DOS-format resume file.
* Corrected errors in autosolvers for rush & dirty12;


**ver 1.1.6 -- 10dec17**

* improved pacman (cpac);
* all games now runnable from home or bin/./ directory;
* The script hipri.bat for Windows was added to fix terminal-freezes by opening a high priority command window for console games.
* Also added scripts hipr.sh (linux & OSX) to run at high priority using "nice", if necessary.


**ver 1.1.5 -- 5dec17**

* added missing DLLs;
* now using the intrinsic file detection function:  Exists();
* elliminated need for directory links, simplifying Windows install.
* huge performance improvements by not erasing screens between redraws.


**ver 1.1.4 -- 29oct17**

* added RPN calculator;


**ver 1.1.4 -- 26oct17**

* added prebuilt executables for msWindows;
* added working build scripts for msWindows;


**ver 1.1.3 -- 18oct17**

* added keymaps for IJKL, WASD, when possible, eg. pacman;
* minor correction to compilation scripts;
* pacman (cpac):
	* now enqueue ONLY valid moves;
	* corrected, improved, simplified movement logic;
* major update to OSX libraries to AdaCore 2017;
* now uses static libraries to simplify build process and enhance robustness;


**ver 1.1.2 -- 2may17**

* added DirtyDozen [external] solver (bfsl.adb) that handles L-shaped blocks.
* embedded autosolvers initiated by the (=)-key into:
	* cdd (DirtyDozen)
	* crush (TrafficRush)
	* cslid (BlockSliders)
	* csok (Sokoban)


**ver 1.1.1 -- 7jan17**

* Added missing libraries for the Gnu/Linux prebuilt binaries.  They should now run even without installing the GNAT GPL Ada compiler, or the GNATColl libraries.
* Still, for MSWin and other OS's, one must install GNAT and rebuild.

**ver 1.1.0 -- 5jan17**

* Now supply prebuild binaries for OS-X and Linux;
* Improved build system.


**ver 1.0.7 -- 20aug16**

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




