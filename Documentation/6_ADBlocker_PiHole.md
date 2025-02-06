# 6. ADBlocker (PiHole)

💡We will use LXC Container with Debian 11 CT Template, 512GB Ram, and 1 core




1. Go to Datacenter > Node > Local > CT Templates > Templates > Debian 11 > Download
2. Create CT > Add specs of 1 core, 512MB ram. And set a static IP. (this ip will be the dns ip too for PiHole which you can connect to block ads).
3. Start CT
4. Type these commands


```
apt update && apt upgrade -y
apt install curl -y
curl -sSL https://install.pi-hole.net | bash
```
1. Now to change the password, type `sudo pihole -a -p`
2. Now open a new tab and enter the IP, followed by /admin
