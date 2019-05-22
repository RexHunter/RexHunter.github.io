# Tmux configuration


## Confirate shared clipboard

### Install addition software

```shell
$ sudo apt-get install -y xclip
```

### Update `~/.tmux.conf` file

Add following lines to configuration *.tmux.conf*

```
bind -t vi-copy y copy-pipe "xclip -sel clip -i"
```

Then just close all tmux sessions and start new session

## Configuare tmux panels shortcuts

### Switching panels with vim shortcuts

Edit ~/.tmux.conf file and add following lines

```
# vim-like pane switching
bind -r k select-pane -U
bind -r j select-pane -D
bind -r h select-pane -L
bind -r l select-pane -R
```

### Resinzing panels with vim shortcuts

Edit ~/.tmux.conf and add following lines

```
# vim-like pane resizing
bind -r C-k resize-pane -U
bind -r C-j resize-pane -D
bind -r C-h resize-pane -L
bind -r C-l resize-pane -R
```

### Disable arrow key

That feature is needed when you use vim shortcuts and arrow is not needed at all.

Edit ~/.tmux.conf and add following lines

```
# unbind arrow keys
unbind Up
unbind Down
unbind Left
unbind Right

unbind C-Up
unbind C-Down
unbind C-Left
unbind C-Right```
```

## Enable mouse control

To be able to use mouse to control tmux window you need to enable it in *.tmux.conf* file.


Edit ~/.tmux.conf and add following lines

For tmux version 2.1 of above add following line to *.tmux.conf*  file

```
# enable mouse control
set -g mouse on

```

For tmux version less then 2.1 you need to add following lines to *.tmux.conf*  file

```
setw -g mode-mouse on
set -g mouse-select-window on
```
