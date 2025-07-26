
# Linux File System Management Summary

## 1. Overview

Linux supports various file systems: `ext2`, `ext3`, `ext4`, `Btrfs`, `XFS`, `NTFS`.

- **ext2**: No journaling, useful for USBs.
- **ext3/ext4**: Journaling; ext4 is default on modern distros.
- **Btrfs**: Snapshots, data integrity.
- **XFS**: High-performance, great for large files.
- **NTFS**: Windows compatibility.

---

## 2. Inodes and Hierarchical Structure

- **Inodes** store metadata (not filenames).
- Think of inodes as catalog cards in a library.
- The **inode table** helps the system track files/directories.

---

## 3. File Types

- **Regular Files**: Text or binary data.
- **Directories**: Containers for other files/directories.
- **Symbolic Links (symlinks)**: Pointers to other files/dirs.

---

## 4. Permissions

Users are divided into:

- **Owner**
- **Group**
- **Others**

Permissions: Read (r), Write (w), Execute (x)

---

## 5. Disk Management with `fdisk`

```bash
sudo fdisk -l
```

Used to list and manage partitions.

---

## 6. Mounting & Unmounting

### Manual Mount

```bash
sudo mount /dev/sdb1 /mnt/usb
```

### Auto-Mount via `/etc/fstab`

```bash
UUID=... /mnt/usb ext4 rw,noauto,user 0 0
```

### View Mounted

```bash
mount
```

### Unmount

```bash
sudo umount /mnt/usb
```

### Check if in use

```bash
lsof | grep /mnt/usb
```

---

## 7. Swap Space

- Used when RAM is full.
- Helps with **memory extension** and **hibernation**.
- Commands:
  - `mkswap`: Format device/file as swap.
  - `swapon`: Enable swap.
- Should be encrypted for security.

---

## 8. Summary Commands

| Command      | Description                                 |
|--------------|---------------------------------------------|
| `fdisk`      | Manage disk partitions                      |
| `mount`      | Mount filesystem                            |
| `umount`     | Unmount filesystem                          |
| `lsof`       | List open files                             |
| `cat /etc/fstab` | Auto-mount config at boot             |
| `mkswap`     | Create swap area                            |
| `swapon`     | Enable swap                                 |

---

Stay organized. Use the right file system for your workload.
