# Fresh Debian 9 Install Steps
1. Gnome Settings
    - Enable dark theme
    - Change time format to 12h
    - Add custom keyboard shortcuts

        | NAME     | COMMAND        | SHORTCUT       |
        | ---      | ---            | ---            |
        | Nautilus | nautilus -w    | Super + E      |
        | Terminal | gnome-terminal | Ctrl + Alt + T |

1. Sudo installation and configuration

    1. Install sudo

        ```
        $ su -
        $ apt-get install sudo -y
        $ exit
        ```

    1. Add regular user to sudoers

        ```
        su -
        adduser denver sudo
        exit
        ```

1. Restart computer

1. Update and upgrade packages

    ```
    sudo apt update
    sudo apt upgrade
    ```

1. Firefox related
    - Change preferences to reopen windows and tabs from last session
    - Install Firefox Extensions
        - Gnome Intergration
        - LastPass

1. Install Gnome extensions
    - AlternateTab (by fmuellner)
    - Drop Down Terminal (by zzrough)
    - Force Quit (by megh)
    - MConnect (by andyholmes) ([DOWNLOAD HERE](https://github.com/andyholmes/gnome-shell-extension-mconnect))
    - Native Window Placement (by fmuellner)
    - Places Status Indicator (by fmuellner)
    - Removable Drive Menu (by fmuellner)
    - ShellTile (by emasab)
    - Suspend Button (by laser_b)
    - User Themes (by fmuellner)

1. Restart computer

1. Configure Gnome extensions

    - Drop Down Terminal

        | TAB      | SETTING                                  | VALUE |
        | ---      | ---                                      | ---   |
        | General  | Transparency                             | 60    |
        | General  | Scrollbar                                | True  |
        | General  | Height                                   | 40%   |
        | Terminal | Run a custom command instead of my shell | True  |
        | Terminal | Custom command                           | fish  |

1. Download user themes
    - Download [Sweet-mars](https://www.gnome-look.org/p/1253385/) (download "sweet-mars" variant) [[Source](https://github.com/EliverLara/Sweet)]
    - Download [Ulimate Maia Orange](https://www.gnome-look.org/p/1253385/) (download "orange" variant) [[Source](https://github.com/bolimage/Ultimate-Maia)]
    - Download [Moka Icon Theme](https://snwh.org/moka/download) [[Source](https://github.com/snwh/moka-icon-theme)]

1. Install user themes
    1. Create the ~/.themes directory if it doesn't already exist. (`mkdir ~/.themes`)
    1. Install Sweet-mars
        1. Unzip "Sweet-mars.tar.xz"
        1. Copy the "Sweet-mars" directory to "~/.themes" (`cp -r Sweet-mars ~/.themes/`)
    1. Install Ultimate-Maia-Orange
        1. Unzip "Ultimate-Maia-Orange.tar.xz"
        1. Copy the "Ultimate-Maia-Orange" directory to "~/.themes" (`cp -r Ultimate-Maia-Orange ~/.themes/`)
    1. Install Moka Icon Theme
        1. Move moka-icon-theme*.deb to a folder for keeping track of installed .debs
        1. `sudo apt install moka-icon-theme`

1. Install Snap (`sudo apt install snapd`)

1. Install Atom via Snap (`sudo snap install atom --classic`)

1. Reboot

1. Launch Atom to continue writing/editing this file

1. Install Git (`sudo apt install git`)
a
1. Configure Git

1. Install Spotify (`sudo snap install Spotify`) **CHANGED TO FLATPAK LATER**

1. Edit /etc/apt/sources.list to include contrib and non-free (`sudo nano /etc/apt/sources.list`)

1. Run apt update (`sudo apt update`)

1. Install nvidia-detect from non-free (`sudo apt install nvidia-detect`)

1. If card is compatible, `sudo apt install nvidia-driver`

1. Reboot the computer

1. Install Stow (`sudo apt install stow`) **REVISIT**

1. Libsecret installation and configuration (for storing github credentials securely) ([original Stack Overflow post](https://askubuntu.com/questions/773455/what-is-the-correct-way-to-use-git-with-gnome-keyring-and-https-repos))

    1. `sudo apt install libsecret-1-0 libsecret-1-dev`

    1. `cd /usr/share/doc/git/contrib/credential/libsecret/`

    1. `sudo make`

    1. `git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret` (configure libsecret as the git credential helper)

1. Install Gparted (`sudo apt install gparted`)

1. Install apt-listchanges (`sudo apt install apt-listchanges`)

1. Install apt-listbugs (`sudo apt install apt-listbugs`)

1. Install htop via Snap (`sudo snap install htop`)

1. Install youtube-dl via Snap (`sudo snap install youtube-dl`)

1. Flatpak installation and configuration

    1. Install flatpak (`sudo apt install flatpak`)

    1. Install software flatpak plugin (`sudo apt install gnome-software-plugin-flatpak`)

    1. Add the Flathub repo (`flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`)

    1. Reboot the system

1. Finish fixing the system after maxing out the storage space in `/` (which is a seperate partition from `/home` for my install) by shrinking my windows partition and expanding my linux system partition

1. Install Kodi via Flatpak (`flatpak install flathub tv.kodi.Kodi`)

1. Install KiCad via Flatpak (`flatpak install --from https://flathub.org/repo/appstream/org.kicad_pcb.KiCad.flatpakref`)

1. Installed Teamviewer from a local deb package

1. Install redshift-gtk (`sudo apt install redshift-gtk`) (ensure location services are enabled under gnome's privacy settings) (when running, make sure you check "autostart" when right-clicking the redshift-gtk icon in the gnome tray)

1. Install discord via Snap (`sudo snap install discord`) (flatpak is offical from discord, snap isn't) (flatpak version crashes a lot however)

1. Uninstall Spotify via Snap

1. Install Spotify via Flatpak (`flatpak install flathub com.spotify.Client`)

1. Installation and configuration of Steam

    1. run this: `sudo dpkg --add-architecture i386`

    1. Install steam (`sudo apt install steam:i386`) (there is a semi-official flatpak version, however Debian's latest stable version of flatpak doesn't support installing it)

    1. If you get the error _"You are missing the following 32-bit libraries, and Steam may not run: libc.so.6"_, try this: `sudo apt install libc6-i386`

    1. If you get the error _"Fatal Error: Failed to load steamui.so"_, try restarting and trying again.

        1. If still recieving errors, try running `steam` from terminal and see if it claims you have any missing libraries.

            - For my specific case, I had to install these packages via apt:
                    `libgl1-mesa-dri:i386`
                    `libgl1-mesa-glx:i386`
                    `libc6:i386`
            - Run `sudo apt install libgl1-mesa-dri:i386 libgl1-mesa-glx:i386 libc6:i386`
            - `sudo apt-get install firmware-linux-nonfree`
            - Reboot
            - Install OpenGL libraries recommended by Debian wiki
                - `sudo apt install libgl1-nvidia-glx:i386`
            - UI now opens without crashing!!! :D

1. Install VLC (`sudo apt install vlc`) (flatpak version cannot install because a newer version of flatpak is required)

1. Get bluetooth headphones working properly

    1. Install requirements [specified by Debian](https://wiki.debian.org/BluetoothUser/a2dp): `sudo apt install pulseaudio pulseaudio-module-bluetooth pavucontrol bluez-firmware` (ensure non-free is in your /etc/apt/sources.list)

    1. Restart bluetooth and pulseaudio services
        `sudo service bluetooth restart`
        `sudo killall pulseaudio`

    1. Install blueman `sudo apt install blueman`

    1. Work-around to fix a2dp_sink profile for High Quality Audio

        1. edit `/var/lib/gdm3/.config/pulse/client.conf` (or create it, if it doesn't exist):
            ```
            autospawn = no
            daemon-binary = /bin/true
            ```

        1. `sudo chown Debian-gdm:Debian-gdm /var/lib/gdm3/.config/pulse/client.conf` (grant access to this file to Debian-gdm user)

        1. `sudo rm /var/lib/gdm3/.config/systemd/user/sockets.target.wants/pulseaudio.socket` (disable pulseaudio startup)

        1. add this to `/etc/pulse/default.pa` (In order to auto-connect a2dp for some devices)
            `load-module module-switch-on-connect`

        1. Reboot ("Now the sound device (bluetooth headset) should be accessible through pavucontrol and standard audio device manager")

1. Install PCSX2 via Flatpak (`flatpak install flathub net.pcsx2.PCSX2`)

1. Install QBitTorrent via Flatpak (`flatpak install flathub org.qbittorrent.qBittorrent`)

1. Install MAME via Snap (`sudo snap install mame`)

1. Download OCS-Store via AppImage and put in `~/Applications` ([Download](https://www.opendesktop.org/p/1175480/) | [Source](https://www.opencode.net/akiraohgaki/ocs-store))

1. Download and install Vimix grub theme

    1. Download [Vimix](https://www.gnome-look.org/p/1009236/) ([Source](https://github.com/vinceliuice/grub2-themes)  + other grub themes)

    1. Move Vimix to a folder with other grub themes

    1. Navigate inside grub-theme-vimix in a terminal, execute `sudo ./install-vimix.sh`

    1. Hate how slow it was

1. Uninstall Vimix grub theme

1. Change grub splash to glass city background in dropbox

1. Installed xboxdrv (`sudo apt install xboxdrv`)

1. Uninstalled xboxdrv

1. Install python3-venv (`sudo apt install python3-venv`)

1. Install python3-dev to fix building wheels (`sudo apt-get install python3-dev`)

1. Install Volux requirements (`sudo apt-get install python3-tk python3-xlib python3-dbus libasound2-dev`)

1. Install/configure requirements for building flatpak packages

    1. Install flatpak-builder (`sudo apt install flatpak-builder`)

    1. Install gnome runtime/platform for flatpak (`flatpak install flathub org.gnome.Platform//3.32`)

    1. Install freedesktop SDK for flatpak (`flatpak install flathub org.freedesktop.Sdk//18.08`)

1. Greatly increase the storage space available in `/` and in `/home` to 25GB and 50GB respectively.

1. Add stretch-backports to sources

    1. Navigate to `/etc/apt/sources.list.d`

    1. Create a new file called `stretch-backports.list`

    1. Put the follow in the file: `deb http://deb.debian.org/debian stretch-backports main`

1. Update flatpak to stretch-backports version (`sudo apt -t stretch-backports install flatpak`)

1. Install kdenlive via Flatpak (`flatpak install flathub org.kde.kdenlive`)

1. Install freetube via Flatpak (`flatpak install flathub io.freetubeapp.FreeTube`)

1. Install LBRY via Flatpak (`flatpak install flathub io.lbry.lbry-app`)

1. Uninstall freetube via Flatpak

1. Install VirtualBox

    1. Navigate to `/etc/apt/sources.list.d` and create the file `virtualbox.list`.

    1. Inside `virtualbox.list`, add this line: `deb https://download.virtualbox.org/virtualbox/debian stretch contrib`

    1. Install apt-transport-https (`sudo apt install apt-transport-https`)

    1. Download public-key file named _oracle_vbox_2016.asc_ from [here](https://www.virtualbox.org/download/oracle_vbox_2016.asc) ([original page](https://www.virtualbox.org/wiki/Linux_Downloads))

    1. Navigate to the directory of _oracle_vbox_2016.asc_ and run this: `sudo apt-key add oracle_vbox_2016.asc`

    1. Install via apt with `sudo apt-get install virtualbox-6.0`

    1. Install OBS via Flatpak (`flatpak install flathub com.obsproject.Studio`)

1. Install WINE (`sudo apt install wine`)

1. Allow user "denver" to access /dev/ttyUSB (`sudo adduser denver dialout`)

    1. Reboot computer

1. Add user "denver" to group vboxusers (`sudo adduser denver vboxusers`)

1. Install nautilus-dropbox (`sudo apt install nautilus-dropbox`)

1. Install xclip (`sudo apt install xclip`) (for storing github SSH stuff)

1. Change fresh-debian-install-steps repo to use SSH instead of HTTPS

1. Set up GPG keys for Github (following information outlined [here](https://help.github.com/en/articles/managing-commit-signature-verification))

    1. Check for existing keys (`gpg --list-secret-keys --keyid-format LONG`)

    2. None? Create one with `gpg --full-generate-key`

    3. When prompted select the default RSA and RSA

    4. Select a keysize of 4096

    5. When prompted for duration, press enter to specify that the key does not expire

    6. Verify your selections are accurate

    7. Make the user ID github username (not essential, just makes sense)

    8. Make the email the no-reply github email address (find this in email settings)

    9. Make the comment specify the os/distro and the machine being used

    10. Enter a passphrase and repeat (take note of it)

    11. Wait 5000 years for the GPG key to generate while wiggling your mouse like a maniac

    12. List your keys to make sure it's all working `gpg --list-secret-keys --keyid-format LONG`

    13. <img src="docs/gpg_key_id_example.png"/>

    14. Run `gpg --armor --export <GPG_key_id>` and copy the output

    15. _"Copy your GPG key, beginning with -----BEGIN PGP PUBLIC KEY BLOCK----- and ending with -----END PGP PUBLIC KEY BLOCK-----"_

    16. Add it to your github account

        1. Go to settings > SSH and GPG keys

        2. Click add new GPG key

        3. In the key field, paste the key you just copied, then click "add GPG key"

        4. Confirm with your github password and you're done! (finally? not really)

    17. Tell git about your new GPG signing key

        1. Copy your GPG key id like before

        2. Run this to let git know about it `git config --global user.signingkey <GPG_key_id>`

        3. _"To add your GPG key to your bash profile, paste the text below:"_

            - `$ test -r ~/.bash_profile && echo 'export GPG_TTY=$(tty)' >> ~/.bash_profile`
            - `$ echo 'export GPG_TTY=$(tty)' >> ~/.profile`

    18. Done!

    19. Nevermind relaunch Atom and try again?

    20. A third time but with CLI instead of Atom?

    21. Follow [this guide](https://help.github.com/en/articles/signing-commits) to make commit signing automatic (in essence though, `git config --global commit.gpgsign true` to sign all local commits across all projects on the machine)

    22. IT FINALLY WORKS! THANK THE LORDS! <img src="docs/gpg_key_victory.png"/>

1. Install VS Code via Snap (`sudo snap install code --classic`)

1. Install KiCad via Flatpak (`flatpak install flathub org.kicad_pcb.KiCad`)

1. Install cabextract so winetricks doesn't throw a fit (`sudo apt install cabextract`) ***STILL NECESSARY? PROBABLY NOT.***

TODO: install fish terminal
