```
set -g prefix C-a
bind C-a send-prefix
unbind C-b

set -g history-limit 100000
set -g allow-rename off

set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'tmux-plugins/tmux-logging'

bind-key j command-prompt -p "Join pane from:" "join-pane -s :'%%'"
bind-key s command-prompt -p "Send pane to:" "join-pane -t :'%%'"

bind \\ split-window -h -c "#{pane_current_path}"
bind - split-window -v -c "#{pane_current_path}"
unbind '"'
unbind %

set-window-option -g mode-keys vi

run-shell /opt/tmux-logging/logging.tmux
run '~/.tmux/plugins/tpm/tpm'
```

- Also do this to enable logging
```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

CTRL+A and SHIFT+I to install logging plugin

CTRL+A SHIFT+P to enable logging in-session
```
9
