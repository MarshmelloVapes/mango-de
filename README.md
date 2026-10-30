# MANGOWC Install

General test of a mango install on arch. Attempt to figure out all packages involved and keep notes. Use final output to create a useable DE to create the required dot files.

# For Testing
qemu-system-x86_64 -enable-kvm -m 4096 -smp 4 \
  -drive file=arch-disk-mango.qcow2,format=qcow2,if=virtio \
  -vga none \
  -device virtio-vga-gl \
  -display gtk,gl=es,show-cursor=on \
  -usb -device usb-tablet

# General Install using archinstall
- Nomrmal install.
- Pipewire
- bluetooth
- etc...

### Packages
kitty bluez bluez-utils bluetui firefox ttf-jetbrains-mono-nerd neovim obsidian base-devel git curl nautilus yt-dlp mpv udisks2 fish starship

## Yay
mkdir ~/.install
cd ~/.install
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si

yay -S fuzzel mangowm-git mangobar-git xdg-desktop-portal-wlr swaybg wl-clip-persist cliphist wl-clipboard wlsunset xfce-polkit swaync pamixer wlr-dpms sway-audio-idle-inhibit-git swayidle dimland-git brightnessctl swayosd wlr-randr grim slurp satty swaylock-effects-git wlogout sox swaybg

## Possibles
sddm

## Commands
sudo systemctl --user enable --now xdg-desktop-portal.service
sudo systemctl --user enable --now xdg-desktop-portal-wlr.service

udisksctl mount -b /dev/mmcblk0p1

