VIBes
=====

[![Build Status](../../actions/workflows/unixmatrix.yml/badge.svg)](../../actions)

**V**isualizer for **I**ntervals and **B**oxes: http://ENSTABretagneRobotics.github.io/VIBES

Get the last version from https://github.com/ENSTABretagneRobotics/VIBES/releases

VIBes is a visualization system that aims at providing people working with interval methods a way to display results (boxes, pavings), without worrying with GUI programming. It provides drawing functions accessible from a lot of programming languages, without complex installation and library dependencies.
The main design goal of VIBes is to be cross-platform, available from different programming languages, simple to set-up, easy to port to a new language.

VIBes consists in two parts:
- the VIBes application that features viewing, annotating and exporting figures
- the VIBes API that enables your program to communicate with the viewer in order to draw figures from C, C++, Python, Matlab...

The use of a separate viewer application enables an easy set-up on every system. First, pre-built binaries of the VIBes viewer are provided for Windows, macOS and Linux platforms (but you are free to build the viewer from sources). Then, the API consists only of a few files that have to be included in your program.

## Building from sources

### Linux

You should have git, cmake, qt5/6 and its svg module installed. On a Debian-like distribution, you can install them via:
```bash
sudo apt-get install qtbase5-dev libqt5svg5-dev cmake git build-essential
```
or
```bash
sudo apt-get install qt6-base-dev libgl1-mesa-dev libqt6svg6-dev cmake git build-essential
```
Note that `qt5-default` package might not be always available nor mandatory. You might also have issues if you have both qt5 and qt6 installed on your system, so try to check carefully which packages you really need.

You can then clone the git repository:

```bash
git clone https://github.com/ENSTABretagneRobotics/VIBES.git
```

Move to the viewer sources directory, and build the sources:

```bash
cd VIBES/viewer
mkdir build && cd build
cmake -DCMAKE_INSTALL_PREFIX=distrib ..
make
make install
```

If everything went well, a `VIBes-viewer` executable is now in the `distrib/bin` folder.

### Windows

See https://community.chocolatey.org/packages/qt6-base-dev to install similar prerequisites as for Linux.

### macOS

See https://brew.sh/ to install similar prerequisites as for Linux (only Intel qt@5 package seems to work for now, use [Rosetta](https://support.apple.com/HT211861) if needed).
