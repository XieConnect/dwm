dwm - dynamic window manager
============================
dwm is an extremely fast, small, and dynamic window manager for X. Current version: v6.0


Usage
-----
* Refer to original installation guide as necessary (included below);
* Customize config.h;
* (optional) Enable system tray by applying attached systray.diff patch;
* Create dwm starter script (eg. dwm_start as attached, with status-bar enabled) in your PATH (eg. /usr/local/bin/). Make sure it's executable;
* Create GDM login option (eg. dwm.desktop as attached) in directory /usr/share/xsessions/ ;
* Install tools of your preference (remember to modify your config.h)
    - termianl: sakura
    - screen lock: slock (or xlock, but it sometimes has problem in wake-up), xautolock (use in combination with slock to auto lock when inactive for certain time)
    - GUI for network management: wicd (start it with wicd-client -n), etc.


Know Issues
-----
* No support for UTF-8 in title bar


Original README in dwm package below
-------

Requirements
------------
In order to build dwm you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install

If you are going to use the default bluegray color scheme it is highly
recommended to also install the bluegray files shipped in the dextra package.


Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm


Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
