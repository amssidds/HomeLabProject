# 2. Creating Linux Bridge

1. Go to Datacenter > Proxmox > System > Network > Create > Linux Bridge > Create
	1. Why not enter anything else? We are telling proxmox to use vmbr0 connection as connection between it and the router. Hence we set the gateway. However for the VMs and LXCs, they would be configured in their own settings to set Firewall as their gateway than the router. So this setting is for Proxmox’s connections, and managing bridges.




