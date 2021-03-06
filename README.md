Configuration files for my desktop environment
================

My current desktop environment is based on Openbox and GNOME.
This page provides information about the software and the settings I use.


Installed software
------------------

Window manager: [Openbox](http://openbox.org)
* Theme: [Adwaita-openbox](http://box-look.org/content/show.php/Adwaita-openbox?content=155042)
* Desktop menu: [obmenu](http://obmenu.sourceforge.net/)
* Logout dialog: [oblogout](https://launchpad.net/oblogout)
* Required for correct virtual desktop number: xorg-xprop

Task bar: [tint2](https://code.google.com/p/tint2/)

Application launcher: [Kupfer](http://engla.github.com/kupfer/)

```
yaourt -S openbox obmenu oblogout tint2 xorg-xprop kupfer
```

System monitor: [Conky](http://conky.sourceforge.net/)
* Fonts: DejaVu Sans, Symbola
* Kernel module to read sound volume: snd-pcm-oss

```
yaourt -S conky ttf-dejavu ttf-symbola
```

Desktop wallpaper (managed by GNOME):
[Grunge Pin by monkeymagico](http://monkeymagico.deviantart.com/art/Grunge-Pin-120293060)

Clipboard manager: [Parcellite](http://parcellite.sourceforge.net/)

```
yaourt -S parcellite
```

This is probably not necessary, but I have installed these programs
on a system with a working GNOME3 desktop environment.

### Optional software

These programs are mentioned here because they are launched automatically
by the Openbox startup script.

Instant messaging client: [Pidgin](http://pidgin.im/)
* SIP/SIMPLE protocol for Microsoft Lync 2010: [SIPE](http://sipe.sourceforge.net/)

Time management: [Hamster Time Tracker](https://projecthamster.wordpress.com/)

Task management: [Getting Things Gnome](https://live.gnome.org/gtg/)

```
yaourt -S pidgin pidgin-sipe hamster-time-tracker gtg
```


Openbox startup script (`openbox/autostart.sh`)
-----------------------------------------------

Programs launched when starting an Openbox session:
* Kupfer
* tint2
* Gnome settings daemon
* Conky
* Gnome screensaver
* Parcellite
* Pidgin
* Hamster time tracker
* Getting Things Gnome

Pidgin is started with NSS_SSL_CBC_RANDOM_IV=0 to prevent an error when connecting to
the Lync server.


Openbox desktop menu (`openbox/menu.xml`)
-----------------------------------------

The menu includes the following items:
* Applications sub-menu, filled automatically by "obm-xdg" (provided by obmenu)
* Reconfigure Openbox
* Quit (launches oblogout)


System monitor (`conky/conkyrc`)
--------------------------------

* Time and date
* CPU load
* Top three programs by CPU load
* RAM free/used
* Top three programs by memory used
* File system free/used (root and home)
* Network speed
* Sound volume


Key bindings (`openbox/rc.xml`)
-------------------------------

* Kupfer (not managed by Openbox): Windows-Space
* Close session (oblogout): Windows-Q
* Show desktop: Windows-D
* Go to previous/next desktop: Ctrl-Alt-Left/Right
* Go do desktop 1 to 6: Windows-F1 to F6
* Move window to previous/next desktop: Shift-Alt-Left/Right
* Close window: Alt-F4
* Toggle maximize/minimize: Alt-F10
* Focus next window: Alt-Tab
* Focus previous window: Alt-Shift-Tab
* Pseudo-tiling: Window-Left/Right/Up/Down
* Toggle full screen: Windows-F

