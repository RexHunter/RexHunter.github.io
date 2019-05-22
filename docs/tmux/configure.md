# Configure tmux clipboard


## Install addition software

```shell
$ sudo apt-get install -y xclip
```

## Update `~/.tmux.conf` file

Add following lines to configuration *.tmux.conf*

```
bind -t vi-copy y copy-pipe "xclip -sel clip -i"
```

Then just close all tmux sessions and start new session



