# 🤖 VPS Crons, Services & Safety Rules (as of 1 Oct 2026)

> Current state after the "cut the noise" change. Back to [[06 - Saranik Growth & Content/Saranik Growth - Master Hub|Master Hub]]

---

## ✅ Active cron jobs

| Time (UTC) | IST | Job | What it does |
| :--- | :--- | :--- | :--- |
| `30 0 * * *` | 06:00 | `saranik-growth/run-daily.mjs` | Research → brief → X drafts for tomorrow |
| `*/5 * * * *` | every 5 min | `saranik-growth/publish/x.mjs` | Posts approved drafts + community cross-posts, verifies live |
| `30 5 * * *` | 11:00 | `saranik-growth/publish/blog.mjs` | Publishes next ready blog + image, verifies live on saranik.in |
| `0 1 * * *` | 06:30 | `influencerScraper.js` | Research scraping only |
| `30 1 * * 0` | Sun 07:00 | `growth-analytics.js` | Weekly analytics |
| `*/30 * * * *` | — | `purge-tmp-profiles.sh` | Cleans browser temp profiles |
| `0 16 * * *` / `0 17 * * *` | — | digest / Hermes report | WhatsApp (Hermes currently broken) |

## ⏸️ Paused (commented `# PAUSED 2026-10-01`) — restore with `crontab -e`
- Calendar tweets 08:00 & 14:00 IST, calendar thread 22:00 IST (M/W/F)
- `post-one.js --saranik` Tue/Wed/Thu/Fri/Sun
- `trend-thread.js` (auto-approved its own threads)
- `community-autopost.js` (old backlog into communities)
- `healthcheck.js` (would auto-restart the stopped reply bot)
- Old saranik blog job `saranik/automation/run-daily.sh` (unapproved daily posts via fake agy)
- Crontab backups: `~/crontab.bak-*`

## 🧩 PM2 services
| Name | Status | Notes |
| :--- | :--- | :--- |
| `xa-web` | 🟢 online | Next.js dashboard, port 9121, `/xagent` |
| `xa-growth` | 🔴 **stopped** | automated replies/likes — keep off |
| `xa-engage` | 🔴 stopped | — |
| `xa-api` | 🟡 "online" but not listening, no DB | real login needs Postgres |

---

## 🛡️ Safety rules enforced in code
1. **Nothing posts without approval** (drafts → Approve in dashboard).
2. `lib/guards.mjs` blocks: links other than saranik.in / wa.me, YouTube mentions, "via @creator", parts >280 chars, `[[FOUNDER]]` gaps.
3. Thread poster aborts if an image isn't attached **inside the composer dialog**.
4. Every post is **verified live on X** (all parts + image); community posts verified inside the community.
5. Failures after posting are **never auto-retried** (no duplicates); pre-post failures retry max 3×.
6. Communities: max 2 of our posts per community per day; composer must show the community name, never "Everyone".
7. Blogs: frontmatter + slug + hero PNG validated; no gaps/bad links; verified live before marked published.

## ⚠️ Open security items
- Rotate the Gemini API key hard-coded in `/usr/local/bin/agy` (fake shim, world-readable).
- Dashboard password was shown in chat once — consider changing (`~/saranik-growth/.env` + Caddy hash).
