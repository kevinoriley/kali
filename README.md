- Complete setup script
```
#!/bin/bash
TMUX_CONF="$(pwd)/.tmux.conf"

{
echo "set -g prefix C-a"
echo "bind C-a send-prefix"
echo "unbind C-b"
echo ""
echo "set -g history-limit 100000"
echo "set -g allow-rename off"
echo ""
echo "bind-key j command-prompt -p \"Join pane from:\" \"join-pane -s :'%%'\""
echo "bind-key s command-prompt -p \"Send pane to:\" \"join-pane -t :'%%'\""
echo ""
echo "bind \\\\ split-window -h -c \"#{pane_current_path}\""
echo "bind - split-window -v -c \"#{pane_current_path}\""
echo "unbind '\"'"
echo "unbind %"
echo ""
echo "set-window-option -g mode-keys vi"
echo ""
echo "run-shell /opt/tmux-logging/logging.tmux"
} > "$TMUX_CONF"

wget https://raw.githubusercontent.com/blacklanternsecurity/kali-setup-script/45e17a71ff02f4dc2728da91bbc9b5c0b287c90c/kali-setup-script.sh

chmod +x kali-setup-script.sh

./kali-setup-script.sh

git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

echo "Press CTRL+A and CTRL+I to install logging. Use CTRL+P to enable logging"
echo "Grab wallpaper from https://github.com/blacklanternsecurity/kali-setup-script/blob/master/bls_wallpaper.png"
```
