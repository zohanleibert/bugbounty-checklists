# Bug Bounty Checklists

> Good recon finds targets.  
> Good methodology finds vulnerabilities.

---

# Recon

- Subdomain Enumeration
- Live Host Discovery
- Port Scanning
- JS File Collection
- Historical URL Collection
- Screenshotting

---

# Subdomain Enumeration

## Tools

```bash
subfinder -d target.com
assetfinder --subs-only target.com
```

## Checklist

- Find hidden subdomains
- Check wildcard responses
- Probe alive hosts
- Look for staging/dev panels

---

# Port Scanning

## Tools

```bash
naabu -host target.com
nmap -sV target.com
```

## Checklist

- Identify uncommon ports
- Detect exposed admin services
- Check outdated versions

---

# URL Collection

## Tools

```bash
gau target.com
waybackurls target.com
katana -u https://target.com
```

## Checklist

- Find old endpoints
- Extract parameters
- Identify sensitive paths

---

# XSS Testing

## Checklist

- Test reflected parameters
- Test search functionality
- Check markdown rendering
- Test file names
- Inspect JS sinks
- Try special characters

---

# IDOR Testing

## Checklist

- Change object IDs
- Test horizontal access
- Test vertical privilege bypass
- Check API endpoints

---

# SSRF Testing

## Checklist

- Test URL input fields
- Check PDF generators
- Test webhook features
- Probe internal IPs carefully

---

# Useful Tools

- httpx
- nuclei
- ffuf
- gf
- qsreplace
- dalfox
- notify

---

# Workflow

```bash
subfinder → httpx → katana → gf → nuclei
```

---

# Notes

- Verify manually.
- Avoid unnecessary noise.
- Automation helps, logic wins.
