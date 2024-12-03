sudo pacman -S git picom flameshot feh thunar polybar zsh p7zip steam neofetch nwg-look noto-fonts-cjk noto-fonts-emoji ttf-font-awesome ttf-iosevka-nerd discord pipewire-alsa pipewire-pulse pavucontrol 

git clone https://aur.archlinux.org/yay.git  
cd yay  
makepkg -si

yay -S ibus-bamboo spotify-adblock spicetify-cli 

sudo chmod a+wr /opt/spotify  
sudo chmod a+wr /opt/spotify/Apps -R  
git clone https://github.com/spicetify/spicetify-themes.git  
cd spicetify-themes  
cp -r * ~/.config/spicetify/Themes  
spicetify config current_theme text  
spicetify config color_scheme Spotify  
spicetify backup apply

cd  /etc/udev/rules.d/  
sudo nvim /etc/udev/rules.d/backlight.rules  
RUN+="/bin/chgrp wheel /sys/class/backlight/intel_backlight/brightness"  
RUN+="/bin/chmod g+w /sys/class/backlight/intel_backlight/brightness"

sudo systemctl start bluetooth.service  
sudo systemctl enable bluetooth.service


