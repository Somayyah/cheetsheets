
My FFMPEG Setup / commands used for many tasks, I only managed to get FFMPEG to work with X11 not WAYLAND.

## Install and enable X11 (tested on Fedora)

```
sudo dnf install xorg-x11-drv-intel xorg-x11-server-Xorg gnome-session-xsession

```

Then edit etc/gdm/custom.conf, and set WaylandEnable to false, like this:

```
WaylandEnable=false
```

Then sign out and back into the user, and make sure X11 is enabled.

## Record screeen with FFMPEG

```
ffmpeg -f x11grab -video_size $(xdpyinfo | grep dimensions | awk '{print $2}') -i $DISPLAY -framerate 60 output.mkv
```
