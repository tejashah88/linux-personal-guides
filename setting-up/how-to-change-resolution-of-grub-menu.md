# How to change resolution of GRUB menu

_Source_: https://unix.stackexchange.com/questions/31672/can-grub-font-size-be-customised

1. Make a backup of the original GRUB configuration.

```bash
sudo cp -a /etc/default/grub /etc/default/grub.bak
```

2. Open the file with your preferred editor (e.g. nano).

```bash
sudo nano /etc/default/grub
```

3. Change `GRUB_GFXMODE` to the preferred resolution (e.g. 1920x1200).

```bash
GRUB_GFXMODE=1920x1200
```

4. Update GRUB with new configuration.

```bash
sudo update-grub
```

5. Reboot your system.
```bash
sudo reboot
```