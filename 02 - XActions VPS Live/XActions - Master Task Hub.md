# ⚡ XActions VPS Live — Master Task Hub

> **Location:** `/Users/garvsanwariya/bounty/xactions-vps-live/`  
> **Scope:** High-volume automated Twitter/X suite (340+ automated tool scripts, Grok AI integration, Direct Messaging pipelines, Ads Manager, and Account Health Monitor).

---

## 🚦 Live Operations & Task Pipeline

### 🔥 Active Tasks & Maintenance
- [ ] **[XA-01] Proxy Rotation & Verification Check**  
  Validate residential and datacenter proxies against Twitter's latest rate limit challenge headers.
- [ ] **[XA-02] Session Token Auto-Renewal**  
  Implement automated auth token validation in `accountHealthMonitor.js` to alert before cookie expiration.
- [ ] **[XA-03] Grok AI Response Polishing in `advancedGrok.js`**  
  Enhance prompt templates for autonomous contextual thread replies and audience engagement.
- [ ] **[XA-04] DM Campaign Throttling**  
  Tune delays in `advancedDM.js` and `adCampaignManager.js` to keep daily delivery velocity within safe account limits.

### 🟡 Core Features & Tool Backlog
- [ ] **[XA-05] Realtime Alert Webhook** (Discord / Telegram alert when account health drops below 80%).
- [ ] **[XA-06] Unify Browser Automation Fallbacks** (`playwright` vs direct HTTP request headers).
- [ ] **[XA-07] Multi-Account Profile Synchronizer**.

### 🟢 Completed Milestones
- [x] **[XA-M1] 340+ Module Suite deployed to VPS**
- [x] **[XA-M2] Core Account Health Monitoring daemon operational** (`accountHealthMonitor.js`)
- [x] **[XA-M3] Ads & Creator tools integrated** (`adsManager.js`, `advancedCreator.js`)
- [x] **[XA-M4] Automated direct messaging pipeline** (`advancedDM.js`)

---

## 🗂️ Component Sub-Pages
1. 🧩 [[02 - XActions VPS Live/XActions - Architecture & Module Index|Complete 340+ Module Index]]
2. 🤖 [[02 - XActions VPS Live/XActions - VPS Daemons & Cron Jobs|VPS Daemons, PM2 & Cron Management]]
3. 🛠️ [[02 - XActions VPS Live/XActions - Tool Backlog & Upgrades|Tool Roadmap & Rate-Limit Hardening]]

---

## 💻 Fast Command Reference
```bash
# Navigate to repository
cd /Users/garvsanwariya/bounty/xactions-vps-live

# Run health check
node accountHealthMonitor.js

# Launch DM Campaign (Dry Run)
node advancedDM.js --dry-run

# Check running daemons (VPS)
pm2 list
pm2 logs xactions-monitor
```
