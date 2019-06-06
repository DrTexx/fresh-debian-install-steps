# Fresh Debian 9 Install Steps

1. Gnome Settings

  - Enable dark theme
  - Change time format to 12h
  - Add custom keyboard shortcuts

    | NAME | COMMAND | SHORTCUT | | --- | --- | --- | | Nautilus | nautilus -w | Super + E | | Terminal | gnome-terminal | Ctrl + Alt + T |

2. Sudo installation and configuration

  1. Install sudo

    ```
     $ su -
     $ apt-get install sudo -y
     $ exit
    ```

  2. Add regular user to sudoers

    ```
     su -
     adduser denver sudo
     exit
    ```

3. Restart computer

4. Update and upgrade packages

  ```
   sudo apt update
   sudo apt upgrade
  ```

5. Firefox related

  - Change preferences to reopen windows and tabs from last session
  - Install Firefox Extensions

    - Gnome Intergration
    - LastPass

6. Install Gnome extensions

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

7. Restart computer

8. Configure Gnome extensions

  - Drop Down Terminal

    | TAB | SETTING | VALUE | | --- | --- | --- | | General | Transparency | 60 | | General | Scrollbar | True | | General | Height | 40% | | Terminal | Run a custom command instead of my shell | True | | Terminal | Custom command | fish |

9. Download user themes

  - Download [Sweet-mars](https://www.gnome-look.org/p/1253385/) (download "sweet-mars" variant) [[Source](https://github.com/EliverLara/Sweet)]
  - Download [Ulimate Maia Orange](https://www.gnome-look.org/p/1253385/) (download "orange" variant) [[Source](https://github.com/bolimage/Ultimate-Maia)]
  - Download [Moka Icon Theme](https://snwh.org/moka/download) [[Source](https://github.com/snwh/moka-icon-theme)]

10. Install user themes

  1. Create the ~/.themes directory if it doesn't already exist. (`mkdir ~/.themes`)
  2. Install Sweet-mars

    1. Unzip "Sweet-mars.tar.xz"
    2. Copy the "Sweet-mars" directory to "~/.themes" (`cp -r Sweet-mars ~/.themes/`)

  3. Install Ultimate-Maia-Orange

    1. Unzip "Ultimate-Maia-Orange.tar.xz"
    2. Copy the "Ultimate-Maia-Orange" directory to "~/.themes" (`cp -r Ultimate-Maia-Orange ~/.themes/`)

  4. Install Moka Icon Theme

    1. Move moka-icon-theme*.deb to a folder for keeping track of installed .debs
    2. `sudo apt install moka-icon-theme`

11. Install Snap (`sudo apt install snapd`)

12. Install Atom via Snap (`sudo snap install atom --classic`)

13. Reboot

14. Launch Atom to continue writing/editing this file

15. Install Git (`sudo apt install git`)

16. Configure Git

17. Install Spotify (`sudo snap install Spotify`) **CHANGED TO FLATPAK LATER**

18. Edit /etc/apt/sources.list to include contrib and non-free (`sudo nano /etc/apt/sources.list`)

19. Run apt update (`sudo apt update`)

20. Install nvidia-detect from non-free (`sudo apt install nvidia-detect`)

21. If card is compatible, `sudo apt install nvidia-driver`

22. Reboot the computer

23. Install Stow (`sudo apt install stow`) **REVISIT**

24. Libsecret installation and configuration (for storing github credentials securely) ([original Stack Overflow post](https://askubuntu.com/questions/773455/what-is-the-correct-way-to-use-git-with-gnome-keyring-and-https-repos))

  1. `sudo apt install libsecret-1-0 libsecret-1-dev`

  2. `cd /usr/share/doc/git/contrib/credential/libsecret/`

  3. `sudo make`

  4. `git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret` (configure libsecret as the git credential helper)

25. Install Gparted (`sudo apt install gparted`)

26. Install apt-listchanges (`sudo apt install apt-listchanges`)

27. Install apt-listbugs (`sudo apt install apt-listbugs`)

28. Install htop via Snap (`sudo snap install htop`)

29. Install youtube-dl via Snap (`sudo snap install youtube-dl`)

30. Flatpak installation and configuration

  1. Install flatpak (`sudo apt install flatpak`)

  2. Install software flatpak plugin (`sudo apt install gnome-software-plugin-flatpak`)

  3. Add the Flathub repo (`flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`)

  4. Reboot the system

31. Finish fixing the system after maxing out the storage space in `/` (which is a seperate partition from `/home` for my install) by shrinking my windows partition and expanding my linux system partition

32. Install Kodi via Flatpak (`flatpak install flathub tv.kodi.Kodi`)

33. Install KiCad via Flatpak (`flatpak install --from https://flathub.org/repo/appstream/org.kicad_pcb.KiCad.flatpakref`)

34. Installed Teamviewer from a local deb package

35. Install redshift-gtk (`sudo apt install redshift-gtk`) (ensure location services are enabled under gnome's privacy settings) (when running, make sure you check "autostart" when right-clicking the redshift-gtk icon in the gnome tray)

36. Install discord via Snap (`sudo snap install discord`) (flatpak is offical from discord, snap isn't) (flatpak version crashes a lot however)

37. Uninstall Spotify via Snap

38. Install Spotify via Flatpak (`flatpak install flathub com.spotify.Client`)

39. Installation and configuration of Steam

  1. run this: `sudo dpkg --add-architecture i386`

  2. Install steam (`sudo apt install steam:i386`) (there is a semi-official flatpak version, however Debian's latest stable version of flatpak doesn't support installing it)

  3. If you get the error _"You are missing the following 32-bit libraries, and Steam may not run: libc.so.6"_, try this: `sudo apt install libc6-i386`

  4. if you get the error _"Fatal Error: Failed to load steamui.so"_, try restarting and trying again.

    **STILL NOT WORKING YET**

40. Install VLC (`sudo apt install vlc`) (flatpak version cannot install because a newer version of flatpak is required)

41. Get bluetooth headphones working properly

  1. Install requirements [specified by Debian](https://wiki.debian.org/BluetoothUser/a2dp): `sudo apt install pulseaudio pulseaudio-module-bluetooth pavucontrol bluez-firmware` (ensure non-free is in your /etc/apt/sources.list)

  2. Restart bluetooth and pulseaudio services `sudo service bluetooth restart` `sudo killall pulseaudio`

  3. Install blueman `sudo apt install blueman`

  4. Work-around to fix a2dp_sink profile for High Quality Audio

    1. edit `/var/lib/gdm3/.config/pulse/client.conf` (or create it, if it doesn't exist):

      ```
       autospawn = no
       daemon-binary = /bin/true
      ```

    2. `sudo chown Debian-gdm:Debian-gdm /var/lib/gdm3/.config/pulse/client.conf` (grant access to this file to Debian-gdm user)

    3. `sudo rm /var/lib/gdm3/.config/systemd/user/sockets.target.wants/pulseaudio.socket` (disable pulseaudio startup)

    4. add this to `/etc/pulse/default.pa` (In order to auto-connect a2dp for some devices) `load-module module-switch-on-connect`

    5. Reboot ("Now the sound device (bluetooth headset) should be accessible through pavucontrol and standard audio device manager")

TODO: install fish terminal
