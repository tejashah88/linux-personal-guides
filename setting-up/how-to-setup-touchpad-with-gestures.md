# How to setup touchpad with gestures

Note: This only applied if your current system uses X11. Wayland should have touchpad gestures working natively.

_Source_: https://github.com/bulletmark/libinput-gestures

0. Ensure that _Python 3.6+_, _libinput 1.0+_, and _Git_ are installed on your system
1. Add your user as a member of the *input* group to give yourself permission to read the touchpad device.

```bash
sudo gpasswd -a $USER input
```

2. Reboot your system.

```bash
sudo reboot
```

3. Install the following dependencies

```bash
sudo apt install wmctrl xdotool
```

* Note: These packages aren't actually required but installing both will ensure maximum compatibility across various configurations (see source for more info).

4. (Debian & Ubuntu only) Install the following dependency

```bash
sudo apt install libinput-tools
```

5. Install the software

```bash
git clone https://github.com/bulletmark/libinput-gestures.git
cd libinput-gestures
sudo ./libinput-gestures-setup install
```

6. Copy the default config file to your home directory

```bash
sudo cp -a /etc/libinput-gestures.conf ~/.config/libinput-gestures.conf
```

7. Open the config file with your preferred editor (e.g. nano) and change as needed.
```bash
sudo nano ~/.config/libinput-gestures.conf
```

Here's an example of how to replicate the virtual desktop functionality from Windows 10. Before you copy-paste the content below, make sure to comment out everything else.
```bash
# Show desktop grid with 3-finger swipe up/down
# Note: The super key is the same as the Windows key or the Command key for Apple.
gesture swipe up        xdotool key super+F8
gesture swipe down      xdotool key super+F8

# Swipe left/right between virtual desktops
gesture swipe left      _internal --wrap ws_up
gesture swipe right     _internal --wrap ws_down
```

8. Test that the gestures are working.

```bash
# Ensure that the program is stopped
libinput-gestures-setup stop

# Test to print out commands that would be executed (<ctrl-c> to stop)
libinput-gestures -d
```

9. Enable it to be autostarted on login and start the service

```bash
libinput-gestures-setup autostart start
```

_Full command reference_: https://github.com/bulletmark/libinput-gestures#starting-and-stopping
