# 🏆 Findings Log & Vulnerability Triage

> Track all discovered security bugs, report statuses, platform tickets, and payout rewards.

---

## 📋 Vulnerability Report Ledger

| Finding ID | Program | Vulnerability Title | Severity | Status | Report Link / ID | Bounty ($) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `FIND-01` | [[03 - Bug Hunting & Security/Programs/Saranik\|Saranik]] | IDOR in Customer Profile Update Endpoint | High | Triaged | `#SA-8821` | Pending |
| `FIND-02` | [[03 - Bug Hunting & Security/Programs/Telenor\|Telenor]] | Stored XSS in Feedback Portal via Unescaped Name | Medium | Resolved | `#TL-4019` | $500 |
| `FIND-03` | [[03 - Bug Hunting & Security/Programs/VDP & CERT-In Programs\|CERT-In]] | Sensitive API Key Exposure in Public JS Bundle | High | Submitted | `#CERT-9102` | HoF |
| `FIND-04` | [[03 - Bug Hunting & Security/Programs/Tesla\|Tesla]] | Rate Limiting Bypass on Reset Password Endpoint | Low | Triaged | `#TS-1049` | $250 |

---

## 📝 Report Template Reference
Use [[05 - Templates/Vulnerability Finding Template|Vulnerability Finding Template]] when filing new bugs.

---

## 🎯 Active Triaging Pipeline
- [ ] Draft PoC video for `FIND-01` and attach Burp HTTP history log.
- [ ] Check fix verification for `FIND-02` on staging domain.
- [ ] Retest reported endpoints after program deployment updates.
