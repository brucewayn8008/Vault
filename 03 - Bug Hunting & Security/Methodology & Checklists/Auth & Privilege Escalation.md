# 🚪 Methodology: Authentication & Privilege Escalation

---

## 🛡️ Broken Access Control (BAC) Verification

### 1. Vertical Privilege Escalation (Member -> Admin)
- Intercept administrative API endpoints (e.g. `/api/admin/users`, `/api/v1/organization/settings`).
- Send request with standard low-privilege session token.
- Look for missing authorization checks on backend controller handlers.

### 2. JWT Vulnerability Checklist
- [ ] **Algorithm None Attack:** Alter header to `{"alg": "none"}` and strip signature.
- [ ] **Weak Secret Cracking:** Run hashcat / jwt_tool on HS256 tokens (`hashcat -m 16500 jwt.txt rockyou.txt`).
- [ ] **RS256 to HS256 Confusion:** Sign JWT with server's public key using HMAC-SHA256.
- [ ] **JKU / JWK Header Injection:** Direct token validation to attacker-controlled keys.

### 3. Password Reset & OTP Weaknesses
- Response manipulation (`{"success": false}` -> `{"success": true}`).
- No rate limiting on 4-digit / 6-digit OTP codes.
- Token leakage in Referer headers or URL query strings.

---

## 🔗 Quick Links
- [[03 - Bug Hunting & Security/Bug Hunting - Master Dashboard|Bug Hunting Dashboard]]
- [[03 - Bug Hunting & Security/Methodology & Checklists/Recon & Asset Discovery|Recon Methodology]]
