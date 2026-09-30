# 🔑 Methodology: API Security & IDOR Checklist

> **The IDOR Principle:** *Never trust the client to identify who is making the request.*

---

## 🔍 Insecure Direct Object Reference (IDOR) Playbook

### 1. Identify Target Object Identifiers
- Numeric IDs (`/api/users/10492`)
- UUIDs (`/api/orders/e2b4f99a-8821-4f12-9c12-3294829910a3`)
- Encoded / Base64 hashes (`/api/invoices?ref=T1JERVIxMjM=`)
- Email parameters (`/api/account/profile?email=victim@target.com`)

### 2. Multi-User Matrix Testing
- Create **User A (Attacker)** and **User B (Victim)** in separate browser profiles (or Caido/Burp sessions).
- Capture legitimate request from User A.
- Replace User A's object ID with User B's object ID while keeping User A's auth token.
- Test across HTTP verbs: `GET` (Read data), `PUT`/`PATCH` (Overwrite data), `DELETE` (Unauthorized deletion).

### 3. IDOR Bypass Tricks
- **Parameter Pollution:** `GET /api/user?id=UserA&id=UserB`
- **JSON Body Injection:** `{"id": "UserB", "user_id": "UserB"}`
- **Method Swapping:** If `GET /api/doc/123` is 403, try `POST /api/doc/123` or `GET /api/doc/123.json`.
- **API Version Downgrade:** If `/api/v2/orders/123` has strict ACL, test `/api/v1/orders/123`.

---

## 🔗 Quick Links
- [[03 - Bug Hunting & Security/Bug Hunting - Master Dashboard|Bug Hunting Dashboard]]
- [[03 - Bug Hunting & Security/Methodology & Checklists/Auth & Privilege Escalation|Auth & Privilege Escalation]]
