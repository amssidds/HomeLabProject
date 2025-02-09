# Home Lab Project

A self-hosted home lab using Proxmox for virtualization, WireGuard for secure remote access, OpenMediaVault for NAS storage, Uptime Kuma for monitoring, and PiHole for ad-blocking.

<p align="center">
  <img width="800" alt="RepoImage" src="https://github.com/user-attachments/assets/75c1aa75-b374-4e37-85b6-15bea7e92aaf" />
</p>

## Directory Structure
```
/
├── Documentation/
│   ├── 1. Proxmox Install
│   ├── 2. Creating Linux Bridge
│   ├── 3. VPN Server (WireGuard)
│   ├── 4. NAS (OpenMediaVault)
│   ├── 5. Uptime Manager (UptimeKuma)
│   ├── 6. ADBlocker (PiHole)
├── Additional Notes/
│   ├── Adding a VM on Proxmox
│   ├── Adding a LXC Container
│   ├── Adding USB_Storage to Proxmox
│   ├── Adding HDDs directly to NAS
│   ├── Why FQDN is used than IP
│   ├── Creating DDNS
```

## Setup Summary
1. **Proxmox** for virtualization (VMs & LXC containers).
2. **WireGuard VPN** for security.
3. **OpenMediaVault** for NAS storage.
4. **Uptime Kuma** for monitoring, **PiHole** for ad-blocking.
5. **pfSense firewall** configured for network security and traffic filtering.

## Toplogy 
```
                           Internet
                               │
                        [ ISP Router ]
                         (192.168.1.1)
                               │
       ┌─────────────────────────────────────────────────┐
       │          Proxmox Virtual Network (`vmbr0`)      │
       │             (Connecting to Firewall)            │
       └─────────────────────────────────────────────────┘ 
                               │
               ┌──────────────WAN──────────────┐
               │     Firewall VM (OPNsense)    |
               │         (192.168.2.1)         |
               └──────────────LAN──────────────┘
                               │
       ┌──────────────────────────────────────────────────┐
       │          Proxmox Virtual Network (`vmbr1`)       │
       │            (Connecting VMs to Firewall)          │
       └──────────────────────────────────────────────────┘
                               │
    ┌─────────────────────────────────────────────────────────────────┐
      [ Web Server ]    [ Honeypots ]    [ VPN Server ]    [ NAS ]
      (192.168.2.10)   (192.168.2.20)   (192.168.2.30)  (192.168.2.40)

```
