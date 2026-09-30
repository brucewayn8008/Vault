# 🏢 Program: {{title}}

**Platform:** HackerOne / Bugcrowd / Intigriti / VDP / Self-Hosted
**Bounty / Swag / Hall of Fame:** Paid Bounty ($)
**Scope Status:** In Scope
**Policy URL:** 
**Created Date:** {{date:YYYY-MM-DD}}

---

## 🎯 Target In-Scope Assets
- `*.domain.com`
- `api.domain.com`
- Mobile Apps: iOS / Android APK

## 🚫 Out of Scope
- Denial of Service (DoS/DDoS)
- Social Engineering / Phishing
- Third-party SaaS without authorization

---

## 🛠️ Tech Stack & Recon Fingerprint
- **Web Server:** Nginx / Cloudflare / AWS CloudFront
- **Backend:** Node.js / Python FastAPI / Spring Boot / PHP
- **Database / Cloud:** AWS S3 / PostgreSQL / Supabase
- **Auth Flow:** OAuth2 / JWT / Session Cookies

---

## 🔍 Attack Surface & Testing Checklist
- [ ] Subdomain enumeration & takeover check (`subfinder`, `httpx`, `dnsx`)
- [ ] Port scan on non-standard ports (8080, 8443, 8000, 9000)
- [ ] Directory & parameter discovery (`ffuf`, `feroxbuster`, `katana`)
- [ ] Authentication, token validation, OAuth redirect manipulation
- [ ] IDOR & Broken Access Control (Horizontal & Vertical privilege escalation)
- [ ] Business logic flaws & race conditions (`Turbo Intruder`)
- [ ] File upload flaws & SSRF via webhook/URL fetchers
- [ ] Nuclei template scan with custom CVEs & exposed panels

---

## 📝 Hunting Log & Session Notes
### Session: {{date:YYYY-MM-DD}}
- **Focus Area:**
- **Requests / Responses / PoC:**
```http

```
- **Result:**
