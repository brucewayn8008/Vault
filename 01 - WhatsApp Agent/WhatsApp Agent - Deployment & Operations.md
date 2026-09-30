# 🚀 WhatsApp Agent — Deployment & Operations

> **Directory:** `/Users/garvsanwariya/bounty/whatsapp_agent/`  
> **Process Architecture:** Background Python process (FastAPI / Uvicorn) + Node.js Baileys Runner

---

## 🛠️ Service Management Scripts

| Script | Purpose | Command |
| :--- | :--- | :--- |
| `start_agent.sh` | Launches backend, initializes environment & starts listener | `./start_agent.sh` |
| `stop_agent.sh` | Gracefully stops all Uvicorn and Node agent instances | `./stop_agent.sh` |
| `logs/agent.log` | Real-time agent event stream | `tail -f logs/agent.log` |

---

## ⚙️ Environment Variables Checklist (`.env`)
- [x] `SUPABASE_URL` — Production Supabase database endpoint
- [x] `SUPABASE_SERVICE_KEY` — Admin key for multi-tenant table access
- [x] `OPENAI_API_KEY` / `GEMINI_API_KEY` — LLM reasoning model keys
- [x] `PORT` — FastAPI port (default `8000`)
- [ ] `LOG_LEVEL` — `INFO` or `DEBUG`

---

## 🛡️ Production Health & Monitoring
- Check process alive: `pgrep -fl uvicorn`
- Check active listening port: `lsof -i :8000`
- Monitor system resource usage: `top -pid $(pgrep -f uvicorn)`

---

## 🔗 Quick Links
- [[01 - WhatsApp Agent/WhatsApp Agent - Master Task Hub|Back to WhatsApp Task Hub]]
