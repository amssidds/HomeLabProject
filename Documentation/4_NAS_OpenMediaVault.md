# 4. NAS (OpenMediaVault)

💡This required a full fledge VM with 1 Core, 4GB Ram




1. Upload the ISO download link through “Download from URL” in Datacenter > Node > local
2. Click “Create VM” and add 2 Cores, 4GB Ram, 125 Storage (you can add more).
3. Follow the steps
4. You will now be given an IP with username and password

# Additional Customizations

1. To Change Password
	1. Click on Profile Pic on top right > Change Password
2. To add more widgets to dashboard,
	1. Click on Profile Pic on top right > Dashboard > Check everything

# Attaching Additional Storage (USB)

1. Go to Datacenter > Node > OMV VM > Storage > Add > USB Device
2. Open OMV VM > Storage > Disk > Refresh > Wipe > EXT4
3. FileSystems > add > select the new usb you added

# Adding Share Folders and giving access

1. Go to Shared Folders > Create > Folder Name > Done
2. Go to Users > Create > username (name) and password > Done
	1. Then back to Shared Folders > User (e.g ameen) > Access Controls > Read-Write > Ok
3. Click Tick on Yellow Message
