# dwm - dynamic window manager
dwm is an extremely fast, small, and dynamic window manager for X.

## Requirements
In order to build dwm you need the Xlib header files and `libxft-bgra`.

## Installation
Edit `config.mk` to match your local setup (dwm is installed into
the `/usr/local` namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install

## Running dwm
Add the following line to your `.xinitrc` to start dwm using `startx`:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY envirmonment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your `.xinitrc`:

    while xsetroot -name "`date` `uptime` | sed 's/.*,//'`"
    do
        sleep 1
    done &
    exec dwm

## Configuration
The configuration of dwm is done by creating a custom `config.h`
and (re)compiling the source code.

## Patches
* actualfullscreen: actually toggles fullscreen for a window
* alwayscenter: spawns all floating windows centered, but without a rule
* attachbelow: makes new clients attach below the selected client
* cfacts: lets you assign different weights to clients in their respective stack
* fullgaps-toggle: adds gaps between client windows
* status2d: allows colors and rectangle drawing in your dwm status bar
* steam: works around the Steam client by ignoring the x and y co-ordinates for ConfigureNotify
