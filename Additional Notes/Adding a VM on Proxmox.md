# Adding a VM on Proxmox

## Steps

1. Download Ubuntu ISO (for example)
2. Navigate to **Proxmox > Datacenter > Node > Local > Content > Upload**
3. **Create a VM:**
    - **Proxmox > Datacenter > Node > Right-click > Create VM**
    - **Configuration:**
        1. Add name
        2. OS > Select ISO
        3. OS > Guest OS - Linux
        4. Hard Disk > Storage - Choose SSD
        5. Hard Disk > Disk Size > 20GB (Recommended)
        6. CPU > Cores - 1 or 2
        7. Memory > 1024MB (Recommended)
        8. Network > Keep existing (if you want the VM on the same network)
        9. Network > DHCP (if option exists)
        10. Finish  
4. **Start the VM:**  
    - Right-click on UbuntuVM > **Start**
5. Follow along and complete the Ubuntu setup.

## Additional Settings

### 1. Memory Ballooning (for efficient RAM usage)
- **Proxmox > Datacenter > Node > Hardware > Memory > Edit > Advanced > Enable Ballooning**
- Set **min and max memory limits** and start the VM.

### 2. Enabling QEMU Guest Agent (to let Proxmox detect the VM's IP)
- **Proxmox > Datacenter > Node > Options > QEMU Guest Agent > Enable**
- Start the VM and run:
    ```bash
    sudo apt-get install qemu-guest-agent
    ```
- Reboot the VM to apply changes.

## Notes

- Choosing a network acts like VLAN segmentation. You can create different networks for specific workloads.

## Resources

[Virtualize Ubuntu Server with Proxmox VE](https://www.youtube.com/watch?v=YR9SNDD8WB4&ab_channel=TechnoTim)
