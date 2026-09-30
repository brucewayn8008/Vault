# 🤖 XActions — VPS Daemons & Cron Jobs

> **Environment:** Ubuntu Linux VPS / Node.js 20+ / PM2 Process Manager

---

## 🕒 Cron Schedule Table

| Time (UTC) | Script | Action | Output Log |
| :--- | :--- | :--- | :--- |
| `*/30 * * * *` | `accountHealthMonitor.js` | Check auth cookies & account safety | `logs/health.log` |
| `0 */2 * * *` | `advancedNotifications.js` | Scan priority mentions & engagements | `logs/notifications.log` |
| `0 9,15,21 * * *` | `adCampaignManager.js` | Fetch ad performance & adjust bids | `logs/ads.log` |
| `0 0 * * *` | `advancedCreator.js` | Daily metrics aggregation | `logs/creator.log` |

---

## ⚡ PM2 Process Control

```bash
# Start monitor daemon
pm2 start accountHealthMonitor.js --name "xactions-health"

# View status & CPU / RAM consumption
pm2 status

# Real-time streaming logs
pm2 logs --lines 100

# Restart all services
pm2 restart all
```

---

## 🛡️ Operational Safeguards
1. **IP Cooldown:** If HTTP 429 is encountered, delay all requests by `Math.floor(Math.random() * 300) + 180` seconds.
2. **Cookie Expiry Alarm:** When `auth_token` returns 401 Unauthorized, automatically send alert webhook to notify for session re-login.
3. **Log Rotation:** Keep maximum 50MB log files to prevent VPS disk fill.

---

## 🔗 Quick Links
- [[02 - XActions VPS Live/XActions - Master Task Hub|XActions Task Hub]]
- [[02 - XActions VPS Live/XActions - Tool Backlog & Upgrades|Tool Backlog & Enhancements]]
