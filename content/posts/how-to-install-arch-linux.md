---
title: "How to install Arch Linux 💻"
date: 2022-04-20T15:44:10+02:00
draft: false
---
Hi there! 😊

I gathered here all the steps that I took to install [Arch Linux](https://archlinux.org/) on my desktop computer.
The main purpose of this post is for personal future reference, but I think (and hope) that someone else might find it useful as well.

### Let's start!

I assume that you are in the installation environment, logged in the first virtual console as the root user, and presented with a Zsh shell prompt. If not, follow the first steps described [here](https://wiki.archlinux.org/title/Installation_guide).

Enable internet access through `iwctl` for Wi-Fi or an Ethernet cable.

```zsh
timedatectl set-ntp true
```

```zsh
fdisk /dev/nvme0n1
mkfs.ext4 /dev/nvme0n1p2
mkfs.fat -F 32 /dev/nvme0n1p1
mkswap /dev/nvme0n1p3
swapon /dev/nvme0n1p3
```

```zsh
mount /dev/nvmen0p1p2 /mnt
mkdir /mnt/boot
mount /dev/nvmen0p1p1 /mnt/boot
```

```zsh
pacstrap /mnt base linux linux-firmware vim iwd dhcpcd networkmanager iproute2
```

```zsh
genfstab -U /mnt >> /mnt/etc/fstab
```

```zsh
arch-chroot /mnt
```

```zsh
ln -sf /usr/share/zoneinfo/Europe/Rome /etc/localtime
hwclock --systohc
```

Edit /etc/locale.gen uncommenting "en\_US.UTF-8 UTF-8"
```zsh
locale-gen
```

Generate: `/etc/locale.conf` with "LANG=en\_US.UTF-8"
```zsh
echo "LANG=en_US.UTF-8" > /etc/locale.conf
```
Generate: `/etc/hostname` with \<your-hostname\>
```zsh
echo <your-hostname> > /etc/hostname
```

Edit /etc/hosts with 127.0.0.1 stuff

```zsh
mkinitcpio -P
systemctl enable --now dhcpcd
systemctl enable --now NetworkManager
passwd
```

```zsh
pacman -S grub
pacman -S efibootmgr
grub-install --target=x86_64-efi --efi-directory=/boot --removable
```

In the new system run:
```zsh
launch this: systemctl enable --now dhcpcd.service
launch this: systemctl enable --now NetworkManager.service
connect with iwctl
```

Add a new user \<user-name\>
```zsh
pacman -S sudo
install zsh
useradd -m <user-name> --shell /bin/zsh
passwd <user-name>
visudo /etc/sudoers (add the following line: "<user-name> ALL=(ALL) ALL")
su <user-name>
```

```zsh
pacman -S xorg
pacman -S gnome
systemctl start gdm.service
systemctl enable gdm.service
exit
```

I didn't install the following, but Arch Wiki suggests to do so:
```zsh
pacman -S intel-ucode
```

Edit `/etc/mkinitcpio.conf` with "MODULES="hid-logitech-hidpp"
Recreate the initrd for the kernel with
```zsh
mkinitcpio -p linux-lts
```

### List of useful packages:

```zsh
pacman -S \
    cmatrix \
    cowsay \
    lolcat \
    terminal-parrot \
    rxvt-unicode \
    youtube-dl \
    base \
    e2fsprogs \
    git \
    htop \
    intel-ucode \
    iproute2 \
    iw \
    iwd \
    less \
    man-db \
    man-pages \
    openssh \
    python \
    sudo \
    textinfo \
    tmux \
    vim \
    zsh
```

### EFISTUB
[EFISTUB](https://wiki.archlinux.org/title/EFISTUB) allows “EFI firmware to load the kernel as an EFI executable”. Despite my motherboard should be able to support EFI firmware, I couldn't find a way to make it works. Since I spent plenty of time trying to figure out what was the problem, I want to put here the command that should have worked for future experimentations:

```zsh
!/bin/sh
blkid -p -o value -s PART_ENTRY_UUID /dev/nvme0n1p2  PARTUUID  # for root parition
efibootmgr --disk /dev/nvme0n1 --part 1 --create --label "Arch Linux" --loader '/vmlinuz-linux-lts' --unicode 'root=PARTUUID=<insert-PARTUUID-here> rw initrd=\initramfs-linux-lts.img' --verbose
```

### Bye, bye! 👋
{{< video src="/homer-arch.mp4" type="video/mp4" preload="auto" width=360 >}}

I hope you have found this post useful somehow. In case you have any questions or comments, please write them below, I'll be happy to discuss with you. In the meanwhile, have a beautiful day! 😊

