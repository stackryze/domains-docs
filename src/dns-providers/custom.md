---
label: Custom DNS
icon: tools
---

# Custom DNS Server Setup

> [!WARNING]
> These docs are in **Beta** and actively updated daily. Please report if you find any issues.

If you prefer to run your own DNS infrastructure, you can use custom DNS servers with indevs Domains. This guide covers the requirements and setup process.

## Requirements

Your custom DNS servers must meet these requirements:

- **Publicly Accessible**: Nameservers must be reachable from the internet
- **Authoritative**: Must be configured as authoritative nameservers for your subdomain
- **Reliable**: Should have good uptime (99%+ recommended)
- **Standard Compliant**: Must follow DNS RFC standards
- **Multiple Servers**: At least 2 nameservers recommended for redundancy

---

## Popular DNS Server Software

### BIND9

**Platform**: Linux, BSD, Windows  
**Difficulty**: Advanced  
**Best For**: Enterprise setups, experienced administrators

[BIND Documentation](https://www.isc.org/bind/)

### PowerDNS

**Platform**: Linux, BSD  
**Difficulty**: Intermediate to Advanced  
**Best For**: Modern setups, API-driven management

[PowerDNS Documentation](https://doc.powerdns.com/)

### NSD

**Platform**: Linux, BSD  
**Difficulty**: Intermediate  
**Best For**: Authoritative-only DNS, security-focused setups

[NSD Documentation](https://www.nlnetlabs.nl/projects/nsd/)

### Knot DNS

**Platform**: Linux, BSD  
**Difficulty**: Intermediate  
**Best For**: High-performance setups, DNSSEC

[Knot DNS Documentation](https://www.knot-dns.cz/)

---

## Setup Overview

### Step 1: Install DNS Server Software

Choose and install your preferred DNS server software on your server(s).

### Step 2: Configure Zone

Create a zone file for your indevs subdomain:

```bind
$TTL 3600
@       IN      SOA     ns1.yourdomain.com. admin.yourdomain.com. (
                        2024010101 ; Serial
                        3600       ; Refresh
                        1800       ; Retry
                        604800     ; Expire
                        86400 )    ; Minimum TTL

; Nameservers
@       IN      NS      ns1.yourdomain.com.
@       IN      NS      ns2.yourdomain.com.

; A Records
@       IN      A       192.0.2.1
www     IN      A       192.0.2.1

; AAAA Records (IPv6)
@       IN      AAAA    2001:db8::1

; CNAME Records
blog    IN      CNAME   yourusername.github.io.
```

### Step 3: Test Your Configuration

Before registering with indevs, test your DNS servers:

```bash
# Test nameserver response

> [!WARNING]
> These docs are in **Beta** and actively updated daily. Please report if you find any issues.
dig @ns1.yourdomain.com yourname.indevs.in

# Test from external resolver

> [!WARNING]
> These docs are in **Beta** and actively updated daily. Please report if you find any issues.
dig yourname.indevs.in @8.8.8.8
```

### Step 4: Register with indevs

Create your registration file:

```json
{
  "owner": {
    "username": "yourgithubusername",
    "email": "your@email.com"
  },
  "record": {
    "NS": [
      "ns1.yourdomain.com",
      "ns2.yourdomain.com"
    ]
  }
}
```

---

## Best Practices

### Use Multiple Nameservers

Always configure at least 2 nameservers for redundancy:
- Primary: `ns1.yourdomain.com`
- Secondary: `ns2.yourdomain.com`

### Geographic Distribution

Place nameservers in different geographic locations for better reliability and performance.

### Monitor Uptime

Use monitoring tools to ensure your nameservers are always available:
- UptimeRobot
- Pingdom
- StatusCake

### Keep Software Updated

Regularly update your DNS server software to patch security vulnerabilities.

### Enable DNSSEC (Optional)

For enhanced security, consider enabling DNSSEC on your nameservers.

---

## Common Issues

### Nameservers Not Responding

**Solution**:
- Check firewall rules (allow UDP/TCP port 53)
- Verify DNS service is running
- Test with `dig @your-nameserver-ip yourdomain.com`

### Zone Not Loading

**Solution**:
- Check zone file syntax
- Review DNS server logs
- Verify zone is properly loaded in configuration

### Slow DNS Resolution

**Solution**:
- Optimize TTL values
- Enable DNS caching
- Check server resources (CPU, memory)

---

## Security Considerations

### Restrict Zone Transfers

Only allow zone transfers to authorized secondary nameservers:

```bind
allow-transfer { 192.0.2.2; };
```

### Rate Limiting

Implement rate limiting to prevent DNS amplification attacks.

### Access Control

Restrict who can update DNS records using:
- TSIG keys
- IP-based ACLs
- API authentication

---

## Monitoring and Maintenance

### Log Analysis

Regularly review DNS logs for:
- Unusual query patterns
- Failed queries
- Security events

### Performance Metrics

Monitor:
- Query response time
- Query volume
- Server resource usage

### Backup Configuration

Regularly backup:
- Zone files
- Configuration files
- DNSSEC keys (if applicable)

---

## Additional Resources

- [DNS RFC Standards](https://www.rfc-editor.org/)
- [BIND Administrator Reference Manual](https://bind9.readthedocs.io/)
- [PowerDNS Documentation](https://doc.powerdns.com/)

---

**Need help?** [Join our Discord](https://discord.gg/wr7s97cfM7) for live help or contact us at [support@stackryze.com](mailto:support@stackryze.com)
