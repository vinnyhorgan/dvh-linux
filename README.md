# dvh's linux setup

> late 2025 edition

**premise**: this setup guide and the config files will be made for my laptop setup and color preference. where possible i will try to remember to specify where changes can be made. an **x86_64 uefi** computer is assumed.

## components:

### core

- **distribution**: [arch linux](https://archlinux.org/)
- **window manager**: [sway](https://swaywm.org/)
- **terminal emulator**: [wezterm](https://wezterm.org/)
- **display manager**: [ly](https://github.com/fairyglade/ly)
- **shell**: [fish](https://fishshell.com/)
- **web browser**: [firefox](https://www.firefox.com/)
- **text editor**: [helix](https://helix-editor.com/)

### wm addons

- **menu**: [tofi](https://github.com/philj56/tofi)
- **notification daemon**: [mako](https://github.com/emersion/mako)
- **status generator**: [i3status-rs](https://github.com/greshake/i3status-rust)
- **workspace namer**: [sworkstyle](https://github.com/Lyr-7D1h/swayest_workstyle)
- **gtk editor**: [nwg-look](https://github.com/nwg-piotr/nwg-look)
- **gamma**: [gammastep](https://gitlab.com/chinstrap/gammastep)

### cli

- **shell prompt**: [starship](https://starship.rs/)
- **ls alt**: [lsd](https://github.com/lsd-rs/lsd)
- **cat alt**: [bat](https://github.com/sharkdp/bat)
- **top alt**: [btop](https://github.com/aristocratos/btop)
- **grep alt**: [ripgrep](https://github.com/BurntSushi/ripgrep)
- **md renderer**: [glow](https://github.com/charmbracelet/glow)
- **file manager**: [yazi](https://yazi-rs.github.io/)
- **system fetch**: [fastfetch](https://github.com/fastfetch-cli/fastfetch)
- **github helper**: [github cli](https://cli.github.com/)

### misc

- **aur helper**: [paru](https://github.com/Morganamilo/paru)
- **power management**: [tlp](https://linrunner.de/tlp/index.html) (if on laptop)

### style

- **color theme**: [catppuccin mocha](https://catppuccin.com/) with **green** accent (on everything)
- **icon theme**: [papirus](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme)
- **monospace font**: [iosevka](https://typeof.net/Iosevka/) (nerd patched)
- **ui sans serif font**: [inter](https://rsms.me/inter/)
- **ui serif font**: [ibm plex serif](https://www.ibm.com/plex/)

### included with archinstall

#### system

- **systemd-boot**: bootloader

#### wm addons

- **swaybg**: wallpaper tool
- **swayidle**: idle daemon
- **brightnessctl**: brightness utility
- **grim** and **slurp**: screenshot utilities
- **xorg-xwayland**: x compatibility layer

#### audio

- **pipewire**: multimedia server
- **pavucontrol**: gui audio mixer

## 0) setup:

to install arch we are going to make use of the [archinstall](https://wiki.archlinux.org/title/Archinstall) script.

we will follow the [official arch installation guide](https://wiki.archlinux.org/title/Installation_guide) up to the point we can safely launch the script.

steps list (wiki for detailed instructions):

- prepare a usb installation medium (**do not skip the checksum and pgp checks**)
- check uefi settings to disable secure boot (while at it make sure all other uefi settings are good)
- boot into the live image
- connect to the internet (either cable or [iwctl](https://wiki.archlinux.org/title/Iwd#iwctl))

if `ping ping.archlinux.org` successfully receives packets, we can safely start the installation using `archinstall`.

## 1) installation

go through the installer filling personal details as requested. for the other options leave default where not specified.

- in **disk configuration** choose `use a best-effort default partition layout` with an `ext4` filesystem
- in **profile** choose `type > desktop > sway`, then for the greeter choose `ly`
- in **applications > audio** choose `pipewire`

that's it! confirm and wait for the installation to finish.

## 2) first boot

- TODO

# extra: desktop configuration

i love the above setup, however, for my nvidia-based main desktop pc with multiple monitors i prefer changing a couple things. the rest stays exactly the same.

## components:

### core

- **window manager**: [kde plasma](https://kde.org/plasma-desktop/)
- **display manager**: [sddm](https://github.com/sddm/sddm)

### wm addons

**none**: plasma is a fully featured desktop environment

## 1) installation

- in **profile** choose `type > desktop > kde plasma`
- in **network configuration** choose `use networkmanager`

## 2) first boot

the only difference here is obviously setting up the desktop environment, which is much easier than the sway setup.

- go through the **system settings** and setup everything as needed
- configure panels and widgets as needed
- install the [catppuccin kde theme](https://github.com/catppuccin/kde) as described on the page, this also applies cursors
- install the [catppuccin sddm theme](https://github.com/catppuccin/sddm) as described on the page

## 3) config

### firefox

add the **plasma integration** extension for better integration.
