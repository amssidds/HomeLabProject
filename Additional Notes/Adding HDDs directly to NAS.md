# Adding HDDs Directly to NAS (OpenMediaVault)

If you have **multiple physical HDDs** connected to **Proxmox** and want to **pass them through to OMV**, follow these steps:

## Step 1: Identify Physical Hard Drives

Run:
```bash
lsblk
```

or
```bash
fdisk -l
```

Locate the HDDs (e.g., `/dev/sdb`, `/dev/sdc`).

## Step 2: Attach Physical Drives to the NAS VM

Run:
```bash
qm set 101 -scsi1 /dev/sdb
qm set 101 -scsi2 /dev/sdc
```

This **directly attaches the physical HDDs** to the OMV NAS VM.

## Step 3: Verify in OpenMediaVault

1. Start the NAS VM:
    ```bash
    qm start 101
    ```
2. Log into **OMV Web UI** → **Storage → Disks**.
3. You should see `/dev/sdb`, `/dev/sdc`, etc.
4. **Format & Mount the drives** in OMV.

💡 **TIP:** If the USB drive does not appear in OMV, go to **Storage > Disks > Select Disk > Wipe**.
