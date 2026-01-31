---
label: Troubleshooting
icon: tools
order: 930
---

# Troubleshooting

> [!WARNING]
> These docs are in **Beta** and actively updated daily. Please report if you find any issues.

Having issues? This guide covers common problems and their solutions.

---

## Login Issues

### "GitHub account too new"

**Error**: Your GitHub account must be at least 7 days old

**Solution**:
- Wait until your GitHub account is 7 days old
- This is a security measure to prevent spam and abuse
- Contact [support@stackryze.com](mailto:support@stackryze.com) if you believe this is an error

---

### "No public email on GitHub"

**Error**: Your GitHub account doesn't have a public email address

**Solution**:
1. Go to [GitHub Settings → Emails](https://github.com/settings/emails)
2. Uncheck "Keep my email addresses private"
3. Or add a public email to your profile
4. Try logging in again

---

### "Account banned"

**Error**: Your account has been banned for violating terms of service

**Solution**:
- Review our [Terms of Service](https://domain.stackryze.com/terms)
- Contact [support@stackryze.com](mailto:support@stackryze.com) if you think this is a mistake
- Include your GitHub username in the email
- **Note:** Banned accounts are immediately logged out on all devices.

---

### "Registration closed"

**Error**: New registrations are temporarily disabled

**Solution**:
- This is rare and usually temporary
- Check our status page for updates
- Try again later or contact support

---

### "Login failed / Server error"

**Error**: Generic login failure

**Solution**:
- Clear your browser cookies and cache
- Try a different browser
- Disable browser extensions temporarily
- Check if GitHub is down: [GitHub Status](https://www.githubstatus.com/)
- Contact [support@stackryze.com](mailto:support@stackryze.com) if the issue persists

---

## Domain Registration Issues

### "Domain name must be at least 3 characters"

**Error**: Your subdomain is too short

**Solution**:
- Use at least 3 characters
- Example: `abc.indevs.in` ✅, `ab.indevs.in` ❌

---

### "Domain name must be less than 63 characters"

**Error**: Your subdomain is too long

**Solution**:
- Keep it under 63 characters
- Use a shorter, more memorable name

---

### "Domain name can only contain lowercase letters, numbers, and hyphens"

**Error**: Invalid characters in subdomain name

**Solution**:
- Use only: `a-z`, `0-9`, and `-`
- No uppercase letters, spaces, or special characters
- Cannot start or end with a hyphen

**Examples:**
- ✅ `my-project`
- ✅ `api2024`
- ❌ `My_Project` (uppercase and underscore)
- ❌ `-myproject` (starts with hyphen)
- ❌ `my project` (spaces)

---

### "Subdomain already exists"

**Error**: Someone else has already registered this name

**Solution**:
- Try a different name
- Add numbers or hyphens: `myproject2`, `my-project`
- Check if it's available first (green checkmark)

---

### "This name is in a cooling-off period"

**Error**: Domain was recently deleted and is in a 7-day waiting period

**Solution**:
- Wait 7 days after deletion
- Choose a different name
- The error message shows how many days remaining

---

### "You have reached your domain limit"

**Error**: You've registered the maximum number of domains (default: 5)

**Solution**:
- Delete unused domains from "My Domains"
- Email [support@stackryze.com](mailto:support@stackryze.com) to request a limit increase
- Include your GitHub username and reason for increase

---

### "At least 2 nameservers are required"

**Error**: You didn't provide enough nameservers

**Solution**:
- Enter at least 2 nameservers
- Most DNS providers give you 2-4 nameservers
- Example: `ns1.example.com`, `ns2.example.com`

---

### "Invalid nameserver format"

**Error**: Nameserver doesn't match valid DNS hostname format

**Solution**:
- Use valid DNS hostnames
- Format: `ns1.example.com` (not `http://ns1.example.com`)
- No spaces or special characters
- Maximum 253 characters per nameserver

**Valid formats:**
- ✅ `ns1.cloudflare.com`
- ✅ `ns-123.awsdns-12.com`
- ❌ `http://ns1.example.com` (no protocol)
- ❌ `ns1 example com` (no spaces)

---

### "Duplicate nameservers are not allowed"

**Error**: You entered the same nameserver multiple times

**Solution**:
- Use different nameservers
- Each nameserver must be unique
- Check for typos

---

### "CAPTCHA verification failed"

**Error**: hCaptcha verification didn't complete successfully

**Solution**:
- Complete the CAPTCHA again
- Make sure you're not using a VPN or proxy
- Try a different browser
- Disable ad blockers temporarily
- Check your internet connection
- Clear browser cache and cookies

---

## DNS & Nameserver Issues

### Nameservers not updating

**Problem**: DNS still points to old nameservers

**Solution**:
1. Wait 5-10 minutes for propagation
2. Clear your DNS cache:
   - **Linux**: `sudo systemd-resolve --flush-caches`
   - **macOS**: `sudo dscacheutil -flushcache`
   - **Windows**: `ipconfig /flushdns`
3. Check with multiple DNS checkers:
   - [DNS Checker](https://dnschecker.org/)
   - [What's My DNS](https://www.whatsmydns.net/)
4. Verify nameservers are correct in dashboard

---

### Domain not resolving

**Problem**: Domain doesn't load or shows DNS errors

**Solution**:
1. Verify nameservers are correctly set in dashboard
2. Check DNS records in your DNS provider (Cloudflare, Route53, etc.)
3. Ensure your DNS provider zone is configured for your subdomain
4. Wait up to 48 hours for global DNS propagation
5. Test with: `dig yourname.indevs.in` or `nslookup yourname.indevs.in`

---

### SSL/HTTPS not working

**Problem**: Browser shows "Not Secure" or SSL errors

**Solution**:
1. Configure SSL in your DNS provider (e.g., Cloudflare)
2. Wait up to 24 hours for certificate provisioning
3. Ensure your origin server supports HTTPS
4. Check SSL mode settings in your DNS provider
5. Verify DNS records point to the correct server

---

## Domain Management Issues

### Can't renew domain

**Problem**: Renew button is disabled

**Solution**:
- You can only renew 60 days before expiry
- Check your domain's expiry date
- If expired, check if it's in the 15-day grace period
- Contact [support@stackryze.com](mailto:support@stackryze.com) if you need help

---

### Accidentally deleted domain

**Problem**: Deleted domain by mistake

**Solution**:
1. **Deletion is permanent** and cannot be undone.
2. You must wait for the **7-day cooling-off period** to complete.
3. After 7 days, the name becomes available for registration again.
4. You will need to re-register the domain.

> [!WARNING]
> Support cannot restore deleted domains. Please be careful when using the Danger Zone.

---

### Domain shows as expired but I renewed it

**Problem**: Status not updating after renewal

**Solution**:
- Refresh the page (Ctrl+F5 or Cmd+Shift+R)
- Clear browser cache
- Log out and log back in
- Wait a few minutes for the database to update
- Contact support if the issue persists

---

## General Issues

### Dashboard not loading

**Problem**: Can't access the dashboard

**Solution**:
1. Check your internet connection
2. Try a different browser
3. Clear browser cache and cookies
4. Disable browser extensions
5. Check if the service is down: [Status Page](https://status.stackryze.com/)

---

### Session expired / Logged out automatically

**Problem**: Keep getting logged out

**Solution**:
1. Enable cookies in your browser
2. Don't use private/incognito mode
3. Check if your browser is blocking third-party cookies
4. Try a different browser
5. Clear cookies and log in again

---

### Changes not saving

**Problem**: Updates to nameservers or settings not saving

**Solution**:
1. Check for error messages on screen
2. Ensure all required fields are filled
3. Verify nameserver format is correct
4. Try again in a few minutes
5. Clear browser cache and retry
6. Contact support with details of what you're trying to change

---

### \"Too many requests\" / Rate limit errors

**Error**: You've exceeded the rate limit for a specific action

**Rate Limits:**
- **Authentication**: 15 attempts per 15 minutes
- **Domain creation**: 2 domains per hour
- **Domain availability checks**: 20 checks per minute
- **General API**: 100 requests per 15 minutes
- **Session checks**: 100 requests per 15 minutes

**Solution**:
1. Wait for the specified time period (shown in error message)
2. Slow down your requests
3. Don't refresh the page repeatedly
4. Don't use automated scripts or bots
5. The error message shows when you can try again

> [!NOTE]
> Rate limits are per IP address and reset automatically after the time window.

---

## Monitoring Issues

### Uptime Kuma / Monitor shows "Offline"

**Problem**: Your site works, but Uptime Kuma or other monitoring tools show it as "Down" (403 Forbidden or 503 Service Unavailable).

**Cause**: Cloudflare's "Under Attack Mode" or "JavaScript Challenge" blocks automated bots, including monitoring tools.

**Solution**: Create a WAF Exception Rule for your monitor.

1. Go to **Cloudflare Dashboard** → **Security** → **WAF**
2. Click **"Create rule"** (under Custom Rules)
3. Set the following:
   - **Rule Name**: `Allow Monitoring`
   - **Field**: `User Agent`
   - **Operator**: `contains`
   - **Value**: `Uptime-Kuma` (or your monitor's name)
   - **Action**: `Skip`
   - **Checkbox**: Select **All remaining custom rules** and **WAF Managed Rules** (or specifically "Super Bot Fight Mode" if available)
4. Click **"Deploy"**

---

## Still Need Help?

If your issue isn't listed here or the solutions don't work:

- 💬 **Discord Community**: [Join for live help](https://discord.gg/wr7s97cfM7)
  - **Fastest way to get help**
  - Live debugging with the community
  - Get answers to quick questions

- 📧 **Email Support**: [support@stackryze.com](mailto:support@stackryze.com)
  - Include your GitHub username
  - Describe the issue in detail
  - Attach screenshots if possible
  - Mention what you've already tried

- 💬 **GitHub Issues**: [Report a Bug](https://github.com/stackryze/domains-docs/issues)
  - For technical issues or bugs
  - Check existing issues first
  - Provide reproduction steps

- 📖 **Documentation**:
  - [Getting Started](getting-started) - Registration guide
  - [Managing Domains](managing-domains) - Domain management
  - [DNS Providers](dns-providers) - DNS setup guides

---

**Response Time**: We typically respond to support emails within 24-48 hours on business days.
