# Creating DDNS (Dynamic DNS)

## Steps

1. Create an account at [Dynu](https://www.dynu.com/).
2. Set up a free DDNS like `myserver.ddnsfree.com`.
3. Configure Proxmox to update your dynamic IP.

Run:
```bash
crontab -e
```

Add this line:
```bash
*/15 * * * * wget -O dynulog -4 "https://api.dynu.com/nic/update?hostname=YOUR_DNS_URL&myip=YOUR_SERVER_PUBLIC_IP&myipv6=no&username=YOUR_USERNAME&password=YOUR_PASSWORD"
```

Replace:
- **YOUR_DNS_URL** (e.g., `myserver.ddnsfree.com`)
- **YOUR_SERVER_PUBLIC_IP** (`curl -4 ifconfig.me` to get it)
- **YOUR_USERNAME**
- **YOUR_PASSWORD**

💡 **To test the update, manually run the wget command. If you see `good` or `nochg`, it’s working!**

This cron job will update your public IP every 15 minutes.
