### Notice: SpriteMage is soon to be reworked using the [FLTK](https://www.fltk.org/) library.
# What is SpriteMage?

SpriteMage is a program to draw sprites for retro-style games.  
The specification is inspired by the SNES, with support for 15 ARGB1555 colors + 1 transparent color per palette.  
  
256 color mode to be added soon.  
  
SpriteMage was stored on my Google Drive until their terms of service threatened my intellectual property.  
  
# Installation

## Installation on Windows

Head over to releases and download the latest SpriteMage.zip, and extract it anywhere on your computer.  
You can run it from its folder.

## Installation on Linux

There are no releases for Linux at the moment, so either download the Windows release and run it with WINE, or try building it yourself. I promise it's easy.

# Building

## Prerequisites

Before you try building SpriteMage all by yourself, make sure you have the correct dependencies installed.  
These are:  

GCC or the GNU Compiler Collection.  
If you're using GNU/Linux, you can install this with your distro's package manager, if it's not already installed.  
If you're on Windows, please use [MinGW](https://www.mingw-w64.org/downloads/).  
  
[SDL2](https://www.libsdl.org/) version greater than or equal to 2.23.0 but less than or equal to 2.30.7, unless you know what you're doing.  
SDL2 version 2.30.8 has bugs with displaying the cursor icons.  
If you're on Linux, you can use your package manager to install the libraries and runtime binaries for this.  
When in doubt, follow their [wiki](https://wiki.libsdl.org/SDL2/FrontPage).  
  
[git](https://github.com/)  
If you don't know how to use git, what are you doing here?  
Install git before trying to clone this. Otherwise, that won't work.  
  
[make](https://www.gnu.org/software/make/) or [Make for Windows](https://gnuwin32.sourceforge.net/packages/make.htm) on Windows  
All that matters is that you install make somehow.  
  
[tinyfiledialogs](https://sourceforge.net/projects/tinyfiledialogs/files/)  
Tiny File Dialogs is already a submodule, so don't fret too much about this one.

## Directory Preparation

This is a platform-agnostic way to prepare the SpriteMage directory so you can build the program.  
  
Clone and cd into the directory, and initialize submodules
```bash
git clone https://github.com/RoseRiver-Code/SpriteMage.git --recurse-submodules
cd SpriteMage
```
Now you can proceed to building!

## Building It Yourself on Linux

Run make
```bash
make
```

If all dependencies were installed correctly, then it should work.

## Building It Yourself on Windows

This guide uses the PowerShell command line.  
If you don't know how to do that, just download the release.

Firstly, download an [SDL2](https://github.com/libsdl-org/SDL/releases) release (correct versions are specified in [Prerequisites](#Prerequisites)) for your compiler. This should look something like "SDL2-devel-2.x.x-mingw.zip".  
Extract the archive somewhere so that you can access the files inside.  
  
Inside the folder, there are two folders to choose from, and you only need one of them.  
One is i686-w64-mingw32, which is for 32-bit x86 computers. You probably won't use this one. The other one (Recommended!!) is x86_64-w64-mingw32, for 64-bit x86 computers. If you have a different CPU architecture, you'll need to build it yourself.  
  
Inside whichever folder you chose, there will be 4 more folders: bin, include, lib, and share.  
In the "bin" folder, there's an SDL2.dll file you should copy into your SpriteMage directory.  
Also, copy the "lib" and "include" folders there as well.
  
Now you should be ready to start building SpriteMage.
  
Open a terminal in the SpriteMage directory, or open PowerShell and cd into it, wherever you put it.  
run make, passing the win32 makefile.  
If you have not added [Make For Windows](https://gnuwin32.sourceforge.net/packages/make.htm) to your path, or installed make in some other way, do so before running this command.
```bash
make -f Makefile.win32
```
Then you can run the executable.  
Congrats, You just built SpriteMage. Enjoy!
