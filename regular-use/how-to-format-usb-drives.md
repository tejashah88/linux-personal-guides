# How to format USB drives

_Source_: https://phoenixnap.com/kb/linux-format-usb

1. Locate the target USB drive.

```bash
lsblk
```

An example drive would have a path like `/dev/sdb1`. If you're unsure, try unplugging the drive, running `lsblk`, replugging it and re-running the command again.

2. Unmount the USB drive.

```bash
sudo umount <path-to-drive>
```

3. Format the USB drive.

```bash
# Format USB drive with the FAT32 file system
sudo mkfs.vfat <path-to-drive>

# Format USB drive with the NTFS file system
sudo mkfs.ntfs <path-to-drive>

# Format USB drive with the exFAT file system
sudo mkfs.exfat <path-to-drive>

# Format USB drive with the ext4 file system
sudo mkfs.ext4 <path-to-drive>
```

4. Verify that the USB is properly formatted.

```bash
sudo fsck <path-to-drive>
```