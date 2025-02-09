# Adding USB Storage to Proxmox

## Step 1: Identify Your USB Drive

Run:
```bash
fdisk -l
```

Your USB device should appear, for example:
- **Device:** `/dev/sda`
- **Partition:** `/dev/sda1`
- **Filesystem:** HPFS/NTFS/exFAT (we will format it to EXT4 for Proxmox compatibility)

---

## Step 2: Unmount the USB (If Needed)
```bash
umount /dev/sda1
```

Ignore any errors if the device isn't mounted.

---

## Step 3: Format the USB to EXT4

⚠ **WARNING:** This erases everything on the USB drive.

```bash
mkfs.ext4 /dev/sda1
```

---

## Step 4: Create a Mount Point

```bash
mkdir /mnt/USB_Storage
```

---

## Step 5: Mount the USB

```bash
mount /dev/sda1 /mnt/USB_Storage
```

Verify the mount:

```bash
df -h
```

---

## Step 6: Make the USB Auto-Mount on Reboot

Find the UUID of the USB:

```bash
blkid /dev/sda1
```

Add the UUID to `/etc/fstab`:

```bash
nano /etc/fstab
```

Append this line:

```
UUID=abcd-1234 /mnt/USB_Storage ext4 defaults 0 2
```

Save and apply:

```bash
mount -a
```

---

## Step 7: Add USB Storage to Proxmox

1. **Go to Proxmox Web UI** (`https://192.168.1.22:8006/`).
2. Navigate to **Datacenter > Storage**.
3. Click **Add > Directory**.
4. Set:
    - **ID:** `USB_Storage`
    - **Directory:** `/mnt/USB_Storage`
    - **Content Type:** `Disk image, ISO, Container, Backup` (as needed).
5. Click **Add**.

🚀 **USB storage is now available in Proxmox!**
