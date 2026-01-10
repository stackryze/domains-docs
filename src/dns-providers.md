---
label: DNS Providers
icon: server
order: 900
---

# Supported DNS Providers

> [!WARNING]
> These docs are in **Beta** and actively updated daily. Please report if you find any issues.

**Stackryze Domains** uses a **Bring Your Own DNS (BYOD)** approach, giving you complete control over your subdomain's DNS configuration. You can use any DNS provider that offers nameserver delegation.

> [!NOTE]
> Currently offering: **indevs.in** subdomains. More domains coming soon!

This page lists popular DNS providers that work well with Stackryze Domains, along with setup guides for each.

---

## Popular DNS Providers

### Cloudflare

**Free Tier**: Yes  
**Features**: Fast global network, DDoS protection, free SSL, analytics  
**Best For**: Most users, beginners to advanced

[Setup Guide →](dns-providers/cloudflare)

---

### AWS Route 53

**Free Tier**: Limited (first 12 months)  
**Features**: Highly reliable, integrates with AWS services, health checks  
**Best For**: AWS users, enterprise applications

[Setup Guide →](dns-providers/route53)

---

### Google Cloud DNS

**Free Tier**: Limited  
**Features**: Low latency, integrates with GCP, DNSSEC support  
**Best For**: Google Cloud users, high-traffic applications

[Setup Guide →](dns-providers/google-cloud-dns)

---

### Azure DNS

**Free Tier**: Limited  
**Features**: Integrates with Azure, high availability  
**Best For**: Microsoft Azure users

[Setup Guide →](dns-providers/azure-dns)

---

### DigitalOcean DNS

**Free Tier**: Yes (with DigitalOcean account)  
**Features**: Simple interface, free with any DigitalOcean service  
**Best For**: DigitalOcean users, simple setups

[Setup Guide →](dns-providers/digitalocean)

---

### Hetzner DNS

**Free Tier**: Yes  
**Features**: Free DNS hosting, simple API, reliable infrastructure  
**Best For**: Hetzner customers, European users

[Setup Guide →](dns-providers/hetzner)

---

### ClouDNS

**Free Tier**: Yes  
**Features**: Free DNS hosting, multiple record types, API access  
**Best For**: Budget-conscious users, small projects

[Setup Guide →](dns-providers/cloudns)

---

### Hurricane Electric (HE.net)

**Free Tier**: Yes  
**Features**: Completely free, IPv6 support, DNSSEC  
**Best For**: Advanced users, IPv6 enthusiasts

[Setup Guide →](dns-providers/hurricane-electric)

---

### Namecheap FreeDNS

**Free Tier**: Yes  
**Features**: Free DNS hosting, easy to use  
**Best For**: Namecheap customers, simple projects

[Setup Guide →](dns-providers/namecheap)

---

### Vercel DNS

**Free Tier**: Yes (with Vercel account)  
**Features**: Automatic SSL, edge network, simple setup  
**Best For**: Vercel users, frontend developers

[Setup Guide →](dns-providers/vercel-dns)

---

### deSEC

**Free Tier**: Yes  
**Features**: Free DNSSEC-enabled DNS, privacy-focused, open source  
**Best For**: Privacy-conscious users, DNSSEC requirements

[Setup Guide →](dns-providers/desec)

---

### PowerDNS (Self-Hosted)

**Free Tier**: Yes (open source)  
**Features**: Self-hosted, API-driven, highly customizable  
**Best For**: Advanced users, custom infrastructure

[Setup Guide →](dns-providers/powerdns)

---

## Choosing a DNS Provider

### For Beginners
We recommend **Cloudflare** for its:
- Free tier with no limitations
- User-friendly interface
- Excellent performance
- Built-in security features

### For AWS Users
**AWS Route 53** is ideal if you're already using AWS services for seamless integration.

### For Budget Projects
**Hurricane Electric** or **Cloudns** offer completely free DNS hosting with no hidden costs.

### For Enterprise
**AWS Route 53**, **Google Cloud DNS**, or **Azure DNS** provide enterprise-grade reliability and SLA guarantees.

---

## General Requirements

All DNS providers must meet these requirements to work with Stackryze Domains:

- **Nameserver Support**: Must provide authoritative nameservers
- **Zone Management**: Ability to create and manage DNS zones
- **Public Accessibility**: Nameservers must be publicly accessible
- **Standard Records**: Support for A, AAAA, CNAME, TXT, MX, and other standard DNS records

> [!TIP]
> Your DNS provider should allow you to create a zone for your subdomain (e.g., `yourname.indevs.in`) and provide at least 2 nameservers.

---

## Need Help?

If you're unsure which DNS provider to choose, check our [FAQ](../faq), join our [Discord Community](https://discord.gg/wr7s97cfM7), or contact us at [support@stackryze.com](mailto:support@stackryze.com).

---

## Contributing

Know a great DNS provider that should be listed here? [Submit a pull request](https://github.com/stackryze/domains-docs) or [open an issue](https://github.com/stackryze/domains-docs/issues).
