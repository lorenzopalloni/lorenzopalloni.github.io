# Arch Linux set up utilities

The following are mini-guides to set up and to troubleshoot some of the issues that I had to deal with using Arch Linux.
Use them with caution. 😉

#### dotfiles
1. Clone the repo https://gitlab.com/dotfiles
2. move all the `./dotfiles/.*` to `$HOME`
3. install and configure [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh#basic-installation).

#### redshift: an alternative to Night Light (Gnome)
```sh
redshift -P -O 4000
```
If it doesn't work, try to run the following (check redshift wiki for more information)
```sh
systemctl enable geoclue-agent.service
```

#### ranger: best file manager ever
```sh
pacman -S ranger
pacman -S w3m  # allow embedded preview
```

#### vim and zsh setup
1. Install gvim (and not vim, because it doesn't have system clipboard support):
```sh
pacman -S gvim
```
2. Install oh-my-zsh (guide in its website)
3. Retrieve your dotfiles:
```sh
git clone https://gitlab.com/loopai/dotfiles
cd dotfiles
mv .vimrc, .zshrc files -t $HOME
```
4. In gnome-terminal:
    Preferences > Profiles:loopai > Colors > check "show bold text in bright colors".

#### Python setup
Download the installer script from https://conda.io/en/latest/miniconda.html.
Run that script, then launch the following:
```sh
conda config --set auto_activate_base false
```

#### Removing title bar in GTK applications (Gnome)
Launch the following and install GTK Title Bar gnome extension
```sh
yay gtktitlebar
```

#### Preventing Gnome to put you in overview at start-up
```sh
yay no-overview
```

#### Checking your current Gnome version
```sh
gnome-software --version
```

#### Gnome title bar size reduction
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

#### How to prevent google-chrome to do weird visual effects
Browse `about:settings` on google-chrome and deactivate the following option:
`Use hardware acceleration when available`

#### How to enhance sound quality of Jabra earbuds (Jabra Elite Active 75t)
```sh
pacman -S pipewire-pulse
pacman -S pipewire-alsa
```
[Here](https://www.reddit.com/r/Jabra/comments/j5489d/if_you_use_jabra_earbuds_with_linux_you_need_to/) an old reference.
Check out the Arch Wiki for more information.

#### How to initialize a GitLab repository from terminal
```sh
cd <project-name>
git init
git branch -m main
git remote add origin https://gitlab.com/loopai/<folder-name>.git
git add --all
git commit -m "First commit"
git push -u origin main
```

#### How to add two remote origin to one repository
```sh
git remote set-url ––add origin https://github.com/<username>/<repo-name>.git
```

