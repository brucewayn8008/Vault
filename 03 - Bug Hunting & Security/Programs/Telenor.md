# 🏢 Program: Telenor

> **Directory:** `/Users/garvsanwariya/bounty/telenor/`  
> **Platform:** Bugcrowd / HackerOne  
> **Reward:** 💰 Cash Bounties ($)

---

## 🎯 Scope & Assets
- Core Domains: `*.telenor.com`, `*.telenor.no`, `*.telenor.se`
- Telecom APIs, self-service portals, customer billing dashboards
- Out of Scope: DoS, social engineering, physical office attacks

---

## 🛠️ Recon Summary & Attack Surface
- Targets list located at `telenor/targets.txt` or root `targets.txt`
- Over 200+ resolved live subdomains running varying stacks (Spring Boot, Angular, Node.js)
- Multi-region routing via Akamai and Cloudflare

---

## 🔍 Testing Checklist for Telenor
- [ ] Subdomain takeover checks on decommissioned marketing portals
- [ ] IDOR testing on subscription management endpoints (`/api/v2/subscriptions/{subId}`)
- [ ] JWT signature validation and algorithm confusion (`alg: "none"`)
- [ ] SSRF via PDF generator / invoice downloader
- [ ] Nuclei scan using `Custom_Vuln_Scan_Templates/`

---

## 📝 Active Session Notes
```
Target: portal.telenor.xxx
Testing: Session cookie fixation and OAuth callback redirection parameters.
Status: Reviewing redirected state tokens.
```

---

## 🔗 Quick Links
- [[03 - Bug Hunting & Security/Bug Hunting - Master Dashboard|Bug Hunting Dashboard]]
- [[03 - Bug Hunting & Security/Findings Log|Findings Log]]
