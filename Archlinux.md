## Ibus reference key change from commandline
gsettings set org.freedesktop.ibus.general.hotkey triggers "['<Alt>Shift_L']"

## Alsa cannot play any sound
sudo setfacl -m u:<username>:rw /dev/snd/*
  
## A better way to manage environment variable for folder
https://github.com/direnv/direnv
