# Why FQDN is Preferred Over IP

1. **Easier to remember** – Employees can remember domain names better than IPs.
2. **Example:** Instead of `192.168.123.456`, you can use `vpn.company.site`.

## How to Configure FQDN?

### Local-Only Access:
1. Create a **DNS Resolver** in your local firewall.
2. Or add the **FQDN to PiHole** to map `vpn.company.site` to `192.168.123.456`.

### External Access:
1. Get a **Static Public IP** (or use DDNS).
2. Create an **A Record** in your domain provider’s DNS settings.

## Benefits:
1. **SSL Compatibility** – Ensures a secure connection.
