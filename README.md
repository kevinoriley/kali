- Complete setup script
- I guess change the home directory path on line 37 if you want the exact same Kali setup as me, for some reason 
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

sudo apt install bluetooth bluez bluez-tools rfkill
sudo systemctl enable bluetooth
sudo systemctl start bluetooth

git clone https://github.com/tmux-plugins/tpm /home/kevin/.tmux/plugins/tpm

wget https://github.com/BloodHoundAD/BloodHound/releases/download/v4.3.1/BloodHound-linux-x64.zip
unzip BloodHound-linux-x64.zip
sudo mv BloodHound-linux-x64 /opt/

sudo apt install pipx
sudo pipx install bbot
sudo pipx ensurepath

sudo apt-get install shutter

echo "-----NEXT STEPS-------------------------------------"
echo "-Press CTRL+A and CTRL+I to install logging"
echo "-Change wallpaper"
echo "-Run kali-tweaks to set console prompt to one-line"
echo "-Install Wappalyzer + FoxyProxy"
echo "-Reduce terminal transparency"
echo "-Install Burp Pro"
echo "-Set up neo4j"
echo "-Pair a bluetooth mouse"
echo "----------------------------------------------------"
```
