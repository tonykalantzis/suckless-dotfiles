#!/bin/bash 
# set wallpaper
exec feh --bg-fill ~/Pictures/pexels-francesco-ungaro-26887889.jpg &x

# Function to manage display status
check_display_status() {
    # Check if DP-1 is connected
    if xrandr | grep -q "DP-1 disconnected"; then
        # If DP-1 is not connected, enable eDP-1 and turn off DP-1
        xrandr --output eDP-1 --auto --output DP-1 --off   
    else
        # If DP-1 is connected, enable it and turn off eDP-1
        xrandr --output DP-1 --auto --output eDP-1 --off 
    fi
}

# Call the function when X starts
check_display_status &

# set hdmi2 monitor in the correct position
#exec xrandr --output HDMI-2 --left-of eDP-1 &
/usr/bin/pipewire &
/usr/bin/pipewire-pulse &
/usr/bin/pipewire-media-session &
exec picom &
exec slstatus &
# enable the module snd-pcm-oss so we can use the volume on slstatus
exec sudo /usr/bin/modprobe snd-pcm-oss & 
exec dwm
