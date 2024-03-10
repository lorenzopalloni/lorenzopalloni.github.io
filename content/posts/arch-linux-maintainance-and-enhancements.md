---
title: "Arch Linux: Maintenance and Enhancements"
date: 2022-04-25T16:41:49+02:00
draft: false
tags: ["arch-linux", "linux", "installation", "arch"]
---
Hi there! 👋

This post is a collection of commands and tips that I have found useful during my journey with Arch Linux.
Use them with caution. 😉

If you would like to install Arch Linux, you can follow the steps described [here](../posts/how-to-install-arch-linux.md).

### Install Vim
Install `gvim` (and not `vim`, because it doesn't support the system clipboard):
```sh
pacman -S gvim
```

I don't remember exactly why, you should tick the following box:
    `Preferences > Profiles:loopai > Colors > check "show bold text in bright colors".`

### Dotfiles Management
Clone a repository containing your dotfiles and move them to your home directory. You can take inspiration from [mine](https://github.com/lorenzopalloni/dotfiles), if you want.
```sh
git clone git@github.com:lorenzopalloni/dotfiles.git
mv ./dotfiles/.* $HOME
```
### Oh-My-Zsh Installation
Install Oh-My-Zsh by running the following command:
```sh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Redshift: an alternative to Night Light (Gnome)
Adjust your screen's color temperature with redshift:
```sh
redshift -P -O 4000
```
If you encounter issues, enabling the geoclue-agent.service might help:
```sh
systemctl enable geoclue-agent.service
```
Check out the [Arch Wiki](https://wiki.archlinux.org/title/Redshift) for more information.

### ranger: a terminal file manager
I love navigating through my files using Vim commands.
```sh
pacman -S ranger
pacman -S w3m  # allow embedded preview
```

### Removing title bar in GTK applications (Gnome)
Launch the following and install GTK Title Bar gnome extension
```sh
yay gtktitlebar
```

### Preventing Gnome to put you in overview at start-up
```sh
yay no-overview
```

### Checking your current Gnome version
```sh
gnome-software --version
```

### Gnome title bar size reduction
1. Copy-paste the content of the above file in `~/.config/gtk-3.0/gtk.css`
2. Run the following command:
```sh
gsettings set org.gnome.Terminal.Legacy.Settings headerbar "@mb false"
```

```css
/*
 * This .css file allows to reduce title bar size of any windows in Gnome.
 * Place the content of this file in:
 * ~/.config/gtk-3.0/gtk.css
 * Then, run the following command:
 * gsettings set org.gnome.Terminal.Legacy.Settings headerbar "@mb false"
*/

/* shrink headerbars */
headerbar {
    min-height: 0px;
    padding-left: 0px; /* same as childrens vertical margins for nicer proportions */
    padding-right: 0px; /* 2px; */
    background-color: #2d2d2d;
}

headerbar entry,
headerbar spinbutton,
headerbar button,
headerbar separator {
    margin-top: 0px; /* same as headerbar side padding for nicer proportions */
    margin-bottom: 0px;
}

/* shrink ssd titlebars */
.default-decoration {
    min-height: 0; /* let the entry and button drive the titlebar size */
    padding: 0px;
    background-color: #2d2d2d;
}

.default-decoration .titlebutton {
    min-height: 0px; /* tweak these two props to reduce button size */
    min-width: 0px;
}

window.ssd headerbar.titlebar {
    padding-top: 0px; /* 3px; */
    padding-bottom: 0px; /* 3px; */
    min-height: 0;
}

window.ssd headerbar.titlebar button.titlebutton {
    padding-top: 0px; /* 3px; */
    padding-bottom: 0px; /* 3px; */
    min-height: 0;
}
```

### How to prevent google-chrome to do weird visual effects
Browse `about:settings` on google-chrome and deactivate the following option:
`Use hardware acceleration when available`

### How to enhance sound quality of Jabra earbuds (Jabra Elite Active 75t)
```sh
pacman -S pipewire-pulse
pacman -S pipewire-alsa
```
[Here](https://www.reddit.com/r/Jabra/comments/j5489d/if_you_use_jabra_earbuds_with_linux_you_need_to/) an old reference.
Check out the Arch Wiki for more information.

#### Initialize a GitLab repository from terminal
```sh
cd <project-name>
git init
git branch -m main
git remote add origin https://gitlab.com/loopai/<folder-name>.git
git add --all
git commit -m "First commit"
git push -u origin main
```

### Add multiple remote origins to your Git repository
```sh
git remote set-url --add origin https://github.com/<username>/<repo-name>.git
```

### Useful command line tools

* exa - https://github.com/ogham/exa
* bat - https://github.com/sharkdp/bat
* ripgrep - https://github.com/BurntSushi/ripgrep
* fzf - https://github.com/junegunn/fzf
* zoxide - https://github.com/ajeetdsouza/zoxide
* entr - https://github.com/eradman/entr
* mc - https://midnight-commander.org/
