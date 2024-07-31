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
echo "set -g @plugin 'tmux-plugins/tpm'"
echo "set -g @plugin 'tmux-plugins/tmux-sensible'"
echo "set -g @plugin 'tmux-plugins/tmux-logging'"
echo ""
echo 'bind-key j command-prompt -p "Join pane from:" "join-pane -s :'\''%%'\''"'
echo 'bind-key s command-prompt -p "Send pane to:" "join-pane -t :'\''%%'\''"'
echo ""
echo 'bind \\ split-window -h -c "#{pane_current_path}"'
echo 'bind - split-window -v -c "#{pane_current_path}"'
echo "unbind '\"'"
echo "unbind %"
echo ""
echo "set-window-option -g mode-keys vi"
echo ""
echo "run-shell /opt/tmux-logging/logging.tmux"
echo "run '~/.tmux/plugins/tpm/tpm'"
} > "$TMUX_CONF"

wget https://raw.githubusercontent.com/blacklanternsecurity/kali-setup-script/45e17a71ff02f4dc2728da91bbc9b5c0b287c90c/kali-setup-script.sh

chmod +x kali-setup-script.sh

./kali-setup-script.sh

sudo apt install bluetooth bluez bluez-tools rfkill
sudo systemctl enable bluetooth
sudo systemctl start bluetooth

git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

wget https://github.com/BloodHoundAD/BloodHound/releases/download/v4.3.1/BloodHound-linux-x64.zip
unzip BloodHound-linux-x64.zip
sudo mv BloodHound-linux-x64 /opt/

sudo apt install pipx
sudo pipx install bbot
sudo pipx ensurepath

echo "-Press CTRL+A and CTRL+I to install logging"
echo "-Grab wallpaper from https://github.com/blacklanternsecurity/kali-setup-script/blob/master/bls_wallpaper.png"
echo "-Run kali-tweaks to set console prompt to one-line"
echo "-Pair a bluetooth mouse"

```
