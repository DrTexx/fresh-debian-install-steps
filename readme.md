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

1. Configure Git

1. Install Spotify (`sudo snap install Spotify`)

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
