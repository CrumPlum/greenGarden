---
title: "Linux - Arch"
Alias: арч, манджаро, polybar, plasma
tags:
- green/seed
date: 2024-07-28 15:01
---
Links:  
[[notes/zero/00 Linux|00 Linux]]

—

### Установка Arch
https://www.youtube.com/watch?v=UbrHwA51lZw&list=PLTcSNhRjVfo1EYR2M48vGebDp9_3srsdE  
setfont cyr-sun16 -d  
ping google.com - пинг  
timedatectl set-ntp true - синх времени  
lsblk - список дисков  
wipefs --all /dev/sda - очистить разделы  
cfdisk /dev/sda - создать разделы  
mkfs.ext4 /dev/sda3 - форматнуть раздел 3  
mkfs.ext4 /dev/sda2 - форматнуть раздел 2  
mount -o defaults,noatime /dev/sda3 /mnt - монтируем раздел  
mkdir /mnt/boot - созд папку  
mount /dev/sda2 /mnt/boot  
приложения  
pacstrap /mnt base base-devel linux-zen linux-zen-headers nano networkmanager plasma egl-wayland  
sddm nftables iptables-nft realtime-privileges dbus-broker intel-ucode(amd-ucode) linux-firmware (nvidia-dkms nvidia-settings) konsole dolphin

genfstab -U /mnt >> /mnt/etc/fstab - генерируем файл с командами  
arch-chroot /mnt  
ln -sf /usr/share/zoneinfo/Europe/Kyiv /etc/localtime - зона  
hwclock --systohc - часы  
sudo nano /etc/locale.gen  
sudo nano /etc/locale.conf  
......  
locale-gen


### ще установка (простіше)  
https://www.youtube.com/watch?v=OJEVBEJsKEQ&list=PLc0sjwKqKpx-EBd0rPcW01-ekFufAnL39&index=1  
archinstall


### красиві теми  
https://wiki.manjaro.org/  
https://catppuccinгарна система.com/ports

### 101 команда  
https://www.youtube.com/watch?v=6EiUGDwjQhI

### plasma

### Polubar
[polybar](https://github.com/polybar/polybar) - крута кастомізована панель, [конфігі полібару](https://github.com/adi1090x/polybar-themes)  
[ютубер](https://youtu.be/9zewiGf7j-A?si=Qc5Fn2RHE2-qnZg7&t=60) про полібар  
https://www.youtube.com/watch?v=E6y-kE1cSvw  
в арч линук ставится: (но краще через офф сайт подивись)

```
mkdir ~/build
cd ~/build
git clone https://aur.archlinux.org/polybar.git
cd ~/build/polybar
makepkg -sri
```

### завантажити та установити linuxARCH(дуал бут і просто)
https://youtu.be/O28sURKsUdA?si=gupUIA_0sOl-uA91  

