![screenshot](https://github.com/fastrgv/CoTerminalApps/blob/master/cinv.png)

![screenshot](https://github.com/fastrgv/CoTerminalApps/blob/master/crush.jpg)

![screenshot](https://github.com/fastrgv/CoTerminalApps/blob/master/puzzles.png)

![screenshot](https://github.com/fastrgv/CoTerminalApps/blob/master/cot.jpg)


# CoTerminalApps
Retro Ascii Character Games that run in a color-capable terminal on Windows, OSX, & Linux.

Grab the large file under "release...latest" for all source and data, or try this link:

https://github.com/fastrgv/CoTerminalApps/releases/download/v2.5.3/co5nov22.7z


then type "7z x filename.7z" to extract the archive.

## Revision Notice: CoterminalApps has been deprecated as of 14nov2022.

* Puzzles have been moved into a new repository named "SliderPuzzles", for puzzle fans only.

* Arcade games were moved into a new repository named "RetroArcade", strictly for gamers.

* The 5nov22 release will remain, but it will be the last.
------------------------------------------------------------------------------------



SpaceInvadersVideo:  https://www.youtube.com/watch?v=dMA4xA4mqII







# CoTerminalApps with Sound, including SpaceInvaders, Frogger, Pacman


## What's new:


**ver 2.5.3 -- 05nov2022**

* Created & enabled embedded "live" solvers for the annoying-sliders and panama apps.
* Improved robustness of all embedded solvers.
* Improved feedback messages in puzzles.
* Fixed a serious error in the Klotski sliders that caused flickering on Windows.


**ver 2.5.2 -- 22oct2022**

* Added 16 annoying block sliders that are small, yet quite challenging.
* Improved traffic-rush by presenting puzzles in order, from easy to hard;
* Similarly improved Klotski-sliders by sorting puzzles from easy to hard; also added Quzzle, Quzzle-Killer puzzles near the difficult end of the scale.
* Improved documentation.



===============================================================
## Introduction

CoTerminalApps is a highly portable collection of non-graphical, ascii-character puzzles & games with sound that run in a commandline terminal on Windows, OS-X and Gnu/Linux. Includes SpaceInvaders, Pacman & Frogger.

-----------------------------------------------------------
Featuring

	* no installation
	* no dependencies (Ncurses not needed)
	* simply unzip in your Downloads directory, or any other writeable directory, and run;
	* or unzip onto a USB flash drive [w/same file format] and run.
-----------------------------------------------------------

The 7zip command to extract the archive and maintain the directory structure is "7z x filename".

* Windows versions use runtime-priority control for arcade-level response.

Rebuildable using the free GNU Ada compiler, even on OSX.

Includes 3 retro arcade games: SpaceInvaders, Pacman, Frogger as well as 10 puzzle games that use ascii characters only:  rush-hour, klotski, flat7, flatAZ, sokoban, hole-in-one, hole-in-one+4, nine, dirty-dozen, panama, annoying-sliders, rpn-calculator.

See the image "./puzzles.png" for a visual of the 10 available puzzzles.

* Two of these puzzles, Flat7 & FlatAZ, are my own creations. They are 2-dimensional versions of my 3D, OpenGL "Rufas Cube" puzzles, available at:  https://sourceforge.net/projects/rufascube/

Usable keys for all:

* arrow-keys for movement; (see ~/docs/KeyboardMoves.txt)
* in some games you can also use wasd, ijkl for moves.
* (q)=quit
* (?)=help toggle

All puzzles & games can be called directly from the command line; e.g.

* bin\w64\cpac.exe	(from base dir)
* cpac.exe				(from ~\bin\w64\ dir)

but it is more convenient to use the selector app, thusly:

* w64term.bat			(Win64)
* macterm.sh			(Mac/OSX)
* gnuterm.sh			(linux)

Use the keyboard arrow keys to highlight the desired game, then press the (enter)-key.

* Windows users note: Using linux executables under WSL [Windows Subsystem for Linux] is not supported. Instead, you should use the windows versions because extraordinary measures have been taken to achieve arcade-level response.

* Similarly, linux users cannot use wine to run Windows executables, with this particular App.

* Many of these 2D slider puzzles are also available in OpenGL-graphical form at: https://sourceforge.net/projects/rufasslider/

* Also using OpenGL graphics, I have created some 3D slider puzzles that run on Windows, OS-X, and Linux. It is available at: https://sourceforge.net/projects/reliquarium/


### For Maximal Enjoyment...
Keyboard setup can be very important for playability.  You should have a very short key-delay and fast repeat rate setting when running the arcade games. The normal settings are fine for puzzles.

Screen setup is important, too. Terminal sizes required:
* pacman:	60x40
* frogger:	56x21
* Invaders:	80x30
* others:	60x25

It is recommended to resize your terminal window, per the above table; then enlarge the font until the window just barely fits your computer screen.

===========================================================================

### CoTerminal-Space-Invaders (cinv.adb)
This is my translation of nInvaders.c into Ada, but with SOUND !!!

You need only the (space)-key to fire your laser gun and the left/right arrow keys [or a-key/d-key] to move out of the way of the alien missiles. The terminal window must be at least 80-chars wide x 30-lines. There are no command-line options, but difficulty increases with level.


### Pacman (cpac)
Pacman, is a kid friendly ascii character version of Pacman that plays in a commandline terminal.  Pure minimalism with classic sounds and 9 predefined levels.  

Now with runtime-priority control to prevent terminal freezes on Windows, plus commandline control of gamespeed & ghostspeed.

Runs on Windows, OSX & Linux.

Keyboard setup is important.  You should have a short key-delay and fast repeat setting.  

The arrow keys, or wasd-keys, or ijkl-keys control movement.  The (x),(q) keys quit;  (p) pauses game.

Includes executables and source code.  Note that this game does NOT require an ncurses library in your environment.

When run directly, cpac can be given 2 optional command line parameters:

	* game speed 0..9; 0=slow, 5=default=medium, 9=fast;
	* ghost speed 0..9; 0=stopped, 2=default=easy, 9=fast.

If you want to try non-default values for these params, you need to run directly from the directory of the executable. To do this: "cd bin/gnu" or "cd bin/osx" or "cd bin\w64", first.

Before running cpac, it is recommended to resize your terminal to 60 chars. wide by 40 lines tall; then, perhaps, enlarge the font.



### Frogger (cfrog)
Terminal frogger is a kid friendly ascii character version of Frogger that plays in a commandline terminal.  Pure minimalism with classic sounds and three levels.

* @@@@ is a raft of lillypads, 
* QQQQ is a team of turtles, 
* ==== is a log, 
* TTT is a truck, 
* ccc is a car.

Runs on Windows, OSX & Linux.

Keyboard setup is important.  You should have a short key-delay and fast repeat setting.

The arrow keys, or wasd-keys, or ijkl-keys control movement.  The (x),(q) keys quit.

Before running cfrog, it is recommended to resize your terminal to 56 chars. wide by 21 lines tall; then, perhaps, enlarge the font.






### CoTerminal-Rush (crush.adb)
Colored, non-graphical Traffic-Rush puzzle game designed to run in a terminal window.

Horizontal and vertical strings of letters represent cars and trucks in a crowded parking garage.  The objective is to move them around lengthwise in order to be able to get red car "a" to the exit, which is either at the right or top of the garage.  Note that the last digits in each puzzle name represents the minimum number of moves to win.

A stand alone autosolver, bfsr, is provided, but now, an autosolver is embedded into this game.  At any time you may press the (=)-key to begin stepping toward a solution.

I created about 20% of these rush-puzzles (filenames that end "my.rush"), including the most difficult one "zzzz_89my.rush".



### BlockSliders, DirtyDozen, AnnoyingSliders
Colored, non-graphical Block Slider puzzle games designed to run in a terminal window.

Colored blocks of letters can be moved horizontally or vertically wherever there is space.  Often, the objective is to move the red block to a specified goal position. Sometimes the goal is to swap the positions of two blocks.

A stand alone autosolver, bfsa, is provided, but now, a "live" autosolver is embedded into these games.  At any time you may press the (=)-key to begin stepping toward a solution.

In cann you must type "0" to restart it, since "r" is reserved to mean "red".

For those times when a solution seems impossible, the more difficult puzzle families have an AutoSolver function using the (=)-key to step closer towards the solution:  crush, cslid, cdd, and cann.  

### Advice to improve puzzle-solving skills:  
Remember that you can **stop** using the autosolvers at any time and try to manually solve the puzzle from a configuration that is a few steps closer to the solution. And because these solvers are "live", you can **resume** using the autosolvers at any time if you get stuck again. Each time you resume, you might need to wait a few seconds for the solver to complete its search.


### Gameplay: crush, cslid, cann (annoying-sliders)

"?" toggles the help screen.  The "+" and "-" keys (next, previous) are used to cycle through the large number of predefined puzzles.  You can reset a puzzle by typing "r". You can autosolve by typing "=". 

First, one selects a vehicle or block by typing its identifier letter.  Then use the arrow keys to move it.  Note that **manual selection is, often times, not necessary,** as there is an auto-select mechanism for those times when only one selection may move in a given direction. For example, cpana never needs a selection (and, btw, it can be solved in 26 moves!).

Be aware that move counts for a given puzzle may differ according to how they are counted. Many puzzzlers count a compound move with a single piece as one move. Here, it is not.

===============================================================
### Seven, A2Z (c7.adb, caz.adb)

c7 (flat7) is a flat representation of a 3D 2x2x2 cube with one cubelet missing that allows sliding permutations.  There are two 2x2 layers. Here, the elements are labelled 1..7.

caz (flatAZ) is a flat representation of a 3x3x3 cube with one cubelet missing that allows sliding permutations.  Here, there are three 3x3 layers. The elements are labelled with the english alphabet.

Flat7 & FlatAZ, are my own creations. They are 2-dimensional versions of my 3D, OpenGL "Rufas Cube" puzzles, available at:  https://sourceforge.net/projects/rufascube/


Both the "caz" and "c7" puzzles work the same:

* note the original order, and blank location;
* mix;
* then restore.

A character in an adjacent row, column, or layer may be moved to the empty space using the keyboard.

Pressing the (home) key on a typical keyboard produces the character 'H'.  So assuming that (home)=>'H', (end)=>'F', (up)=>'A', etc...
the KEY MAPPING follows:

* (1)..(5): mix;  higher values are more difficult.
* (up),(lf),(dn),(rt): move north, west, south, east
* (i),(j),(k),(l): move north, west, south, east
* (w),(a),(s),(d): move north, west, south, east
* (home),(end): move up one layer, down one layer
* (\\),(/): [backslash=]move up one layer, [forwardslash=]down one layer
* (-),(+): move up one layer, down one layer
* (?): help
* (q): quit



===============================================================

### CoTerminal-sokoban (csok.adb)
There are now two character sets possible that are toggled with the (c)-key.

Move the pusher ( <> or @ ) with the arrow keys in order to push all the boxes ( [] or $ ) onto the goals ( :: or . ) in which case they look like ( {} or asterisk ).  Various other functions available on the help screen.  Includes a very large family of puzzle files.

Three [external] sokoban solvers named iplr3r, ibox3r, & hbox4  are available.  The command line is "solver-name puzzle-file-name level-number-to-solve".  The solvers print solution-strings to the terminal screen.

There are many cases the first two solvers cannot handle, but they are pretty good at solving smaller puzzles, particularly the more dense ones. Hbox4 is the most capable.

Three time-limited-to-10-second solvers are embedded into csok.  At any time you may press the (=)-key to see if the solver #1 can help you.  If so, you will be prompted to keep pressing that same key to proceed toward a solution.  No prompt means either the present state is unsolvable, or merely that the embedded algorithm failed.  Similarly, the (.)-key initiates solver #2; and the (,)-key initiates solver #3. These can give you a headstart toward a correct solution by limited use of this feature.  Once you think you can solve it yourself, stop using the solver and proceed manually.  This really helps when you cannot see what your next move should be.


### CoTerminal-HoleInOne (chio.adb, chio4.adb)
Move the red 2x2 'a' block into the center of the four L-shaped corner pieces.

### CoTerminal-Nine (c9.adb)
Reverse the order of the numbered blocks with assorted shapes. First version begins with blocks in order. Second begins with blocks in reverse order. Has solver.

### RPN (reverse polish notation) command line calculator
A cult classic.  Recalls the HP rpn functionality. **As a bonus, this version uses differentials to calculate an error estimate.** No longer accesible through the selector app, one must call it directly, eg.

	* bin\w64\rpn.exe
	* bin/gnu/rpn
	* bin/osx/rpn

===============================================================
## Setup & Running:

CoterminalApps is a stand-alone application.
Ncurses is NOT needed; there are no prerequisites.

Mac users see "osx-setup.txt".
Windows users see "windows-setup.txt".

Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this.
The proper command to extract the archive and maintain the directory structure is "7z x filename".

Open a commandline terminal, and cd to the game directory.

Arcade games require your keyboard to have a short key-delay and fast repeat rate.

Minimize the size of your terminal window:

* pacman:	60x40
* frogger:	56x21
* Invaders:	80x30
* others:	60x25

Then enlarge the Font so that the window fills your monitor.

To launch the game selector App, depending on your system, type:

* w64term.bat (win64)
* macterm.sh (OSX)
* gnuterm.sh (linux)

Note that any individual app may still be executed from the directory appropriate to your O.S.  For example, on Windows you can CD to bin\w64 and then type "cfrog" to run Frogger.



### OSX caveat
The prebuilt OSX executables require version 10.13 (sep2017) or newer.

===========================================================================
## Compiler Scripts
There are 3 scripts, w64buildall.bat for Windows, lbuildall.sh for Linux, and obuildall.sh for OS-X.  They differ in where the executables are put.  With so many different precompiled binaries for each OS, there would be too much clutter if they were all put into the same place, particularly since windows needs colocated DLLs.

These build scripts work for GNU Ada [with its own g++].
See ./alternateBuildScripts/ for more examples.

The latest scripts have elliminated the need to use the "gnatcoll" library simply by compiling from source 3 additional tiny files, a small subset of gnatcoll, that are actually used by CoterminalApps.

Final note:  the latest OSX script does not use Xcode, only GNU Ada & GNU g++.

==========================================================================
## Build Instructions:
Remember that prebuilt executables are already included. But, if you want or need to rebuild...


To get a recent Ada compiler;  eg. GNU-Ada...try this source:

https://github.com/alire-project/GNAT-FSF-builds/releases


Manually install GNU Ada.  If you don't like my key-mappings, edit the code as you like.

Next, edit the scripts w64cmp.bat, lcmp.sh or ocmp.sh so that the path to gnatmake is correct.  These scripts streamline the build process by allowing auxilliary files to be neatly hidden in subdirectories.

Windows users please read gnuAdaOnWindows.txt.

Then type "[w64/l/o]buildall" to create new command-line executables for your system. ( w64 for Windows, l for Linux, o for OSX). 

There are NO other 3rd party libraries or tools required to build.




---------------------------------------------------------------

## What is special about this project?...freedom...portability

* uses the Ada programming language and the freely-available GNU compiler.
* runs on Macs running OSX, or PCs running Windows or Linux;
* uses only free open source software [F.O.S.S] tools & libraries;
* portable, transparent code, easy to modify, rebuild;
* uses a cross-platform implementation of OpenAL-Audio, adaptable by any Ada application that needs sounds & music-loops with a simple interface.
* pure minimalism:  no graphics, just colored ASCII characters, keyboard, & sound;
* Ncurses is <u>not</u> required.

Open source Ada developers are welcome to help improve or extend this app.
Developer or not, send comments, suggestions or questions to:
fastrgv@gmail.com


---------------------------------------------------------------


## License:

CoTerminalApps is covered by the GNU GPL v3 as indicated in the sources:

 Copyright (C) 2022  <fastrgv@gmail.com>

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

Sebastian Gutsfeld [segoh@gmx.net]  & Alexander Hollinger [alexander.hollinger@gmx.net] for the C-version of nInvaders (v0.1.1), after which this Ada version was modelled (gnu gpl).

Nick Baxter, J.H.Conway, Jim Lewis, Bob Henderson, Gil Dogon, Ed Pegg Jr., J.I. Wiley, J.H. Fleming, C. L. Diamond, Sam Loyd, H. E. Dudeney, E. B. Escott, Nob Yoshigahara, James W. Stephens for the classic sliders.


----------------------------------------------
### SoundFiles (wav)
Fanfare/Applause and UFO sounds are from freesound.org and are covered by the Creative Commons CC0 Public License documented in the accompanying file ./docs/creativeCommonsCC0.txt. A few have a CC-by-3.0 license and are accompanied by a text file with the attribution.

Others from 
* classicgaming.cc/classics/pac-man/sounds
* classicgaming.cc/classics/frogger/sounds
(also CreativeCommons cc0).
The remaining sounds are public domain.
See also: ./sounds/licenses-sound-data.txt.

It is my intention to use media with copyrights or licenses that are compatible with GPLv3. Please notify me if you believe there is an incompatibility, and it will be removed; eg a CC-by-NC license is NOT GPL compatible.




----------------------------------------------
## Download Sites for all my games:
* https://github.com/fastrgv?tab=repositories
* https://www.indiedb.com/members/fastrgv/games
* https://fastrgv.itch.io
* https://sourceforge.net/u/fastrgv/profile/
* https://gamejolt.com/@fastrgv/games


## Video BlockSlider Autosolve:
* https://youtu.be/dD3VGbXv3ng

--------------------------------------------------
## Some Earlier Revision History:


**ver 2.5.1 -- 26sep2022**

* Simplified Win64 build; using new stand-alone GNU Ada compiler.
* Removed Win32 build because embedded sokoban solvers need maximal memory.
* Removed all gnatcoll libraries by compiling from source the tiny subset needed.

**ver 2.5.0 -- 20sep2022**
* Restored Win64 build, now using MSYS2 & mingw64 on Windows.
* Still deliver Win32 build, also.

**ver 2.4.1 -- 16sep22**
* Removed Win64 build.
* Now using GNU Ada rather than defunct AdaCore compiler.

**ver 2.4.0 -- 23dec21**
* Updated gnatcoll libraries on OSX & w32; removed unused libgpr.a.
* All "assets", including datafiles & soundfiles, now have licenses compatible with the GPLv3 license.

**ver 2.3.9 -- 05nov21**
* Added example script to build using Gnu/Gnat.
* Refined libraries and build scripts.
* Replaced libgnatcoll.a with one from GitHub.

**ver 2.3.8 -- 21oct21**
* Besides Win64, there is now a Win32 build, to support older platforms.
* Improved adaOpenAL binding code.

**ver 2.3.7 -- 18oct21**
* Eliminated anomalous clutter in nexus selection app;
* Arcade-games now pause to show stats before exitting.

**ver 2.3.6 -- 07oct21**
* SpaceInvaders:
	* New red aliens shape.

**ver 2.3.5 -- 06oct21**
* SpaceInvaders:
	* New UFO shape; new alien shapes; aliens harder to hit.

**ver 2.3.4 -- 29sep21**
* SpaceInvaders:
	* New UFO sound (less annoying);
	* More aliens (11 across, like original).


**ver 2.3.3 -- 28sep21**
* SpaceInvaders:
	* Improved logic to eliminate color errors;
	* Added high-valued, bidirectional UFO.
	* Made first level easier; higher levels harder.

**ver 2.3.2 -- 26sep21**
* SpaceInvaders Improvements:
	* refined screen drawing indexes to eliminate anomalies.
	* added gameover sound.
	* added checks to assure screen-draws are synched with motions.
	* added final screen-clear to play nicely with selection app.

**ver 2.3.1 -- 24sep21**
* SpaceInvaders Improvements:
	* refined timing params for improved & reliable action.
	* added sound when player loses life;
	* added output of number of lives remaining;
	* made first level easier;
	* each susequent level has increasing alien speed & number of missiles.

**ver 2.3.0 -- 22sep21**
* Added SpaceInvaders arcade game [cinv].
* Fixed critically bad indexing in "nexus" selection app.

**ver 2.2.4 -- 16may21**
* csok: added more puzzle files.
* csok: fixed u-key [undo] problem.
* csok: added o-key to restart puzzle.
* added c9r, reverse-mode c9.
* improved help messages.

**ver 2.2.3 -- 10mar21**
* c7,c9,caz now have solvers & improved screens.
* c7,caz now allow restart using (r)-key.
* nexus/puzzles.txt now limited to 60 columns.

**ver 2.2.2 -- 06mar21**
* Csok now has alternate character set toggled with (c)-key.
* Csok now has 3 embedded autosolvers.

**ver 2.2.1 -- 23feb21**
* Updated sokoban autosolvers & csok.
* Added more capable hbox4 sokoban solver.
* Improved build scripts.

**ver 2.2.0 -- 8nov20**
* Completely revised & enhanced sound system; 
* Using cross-platform OpenAL binding;
* Simplified build process & coding;
* Pacman background music now restored.

**ver 2.1.0 -- 26oct20**
* Improved UI for RPN-calc.

**ver 2.0.4 -- 22sep20**
* Game-launcher now allows (return)-key to select, uses improved colors.

**ver 2.0.3 -- 23jun20**
* All apps are now launched using a single command.







