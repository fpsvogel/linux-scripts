#!/bin/sh

# Upon unlocking after wake, lower the laptop screen brightness because it
# mysteriously switches back to full brightness at that point. I use an
# external monitor as my primary, and I prefer to keep the unused laptop
# monitor at low brightness. From https://unix.stackexchange.com/a/567213
dbus-monitor --session "type='signal',interface='org.cinnamon.ScreenSaver'" | \
(
  while true; do
    read X
    if echo $X | grep "boolean false" &> /dev/null; then
      sleep 5; xdotool key XF86MonBrightnessDown
    fi
  done
)
