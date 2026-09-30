# 📱 WhatsApp Agent — Master Task Hub

> **Location:** `/Users/garvsanwariya/bounty/whatsapp_agent/`  
> **Stack:** FastAPI (Python), Baileys / WhatsApp Multi-Device Session, Next.js Console, Supabase Postgres

---

## 🚦 Task Pipeline Board

### 🔥 High Priority / Blocking (Current Sprint)
- [ ] **[WA-01] Server-side Filtering & Pagination on `/agent/logs`**  
  Add query params `?event_type=&exclude=&limit=&cursor=`. Currently ~18k rows (`group_message_skipped`, `agent_step`) flood the client.
- [ ] **[WA-02] Query Params on `/leads` Endpoint**  
  Add `status`, `needs_response`, `human_takeover`, `q`, `sort`, `limit`, `cursor`. Eliminate full dataset refetches on filter switch.
- [ ] **[WA-03] Discard Endpoint for Held Drafts**  
  Implement `DELETE /messages/{id}` or `POST /drafts/{id}/discard` so users can reject held drafts cleanly without sending.
- [ ] **[WA-04] Authoritative `needs_response` Field in Lead Schema**  
  Expose `needs_response` computed server-side instead of relying on frontend client-side timestamp comparison (`last_inbound_at > last_outbound_at`).

### 🟡 Mid Priority (Core Polish & Feature Set)
- [ ] **[WA-05] Unify Log Endpoints**  
  Consolidate `/agent/logs`, `/agent-logs`, and `/system-logs` into one authoritative endpoint.
- [ ] **[WA-06] Real-time SSE / WebSocket Feed**  
  Replace UI polling loops with Server-Sent Events for activity feed and live conversation logs.
- [ ] **[WA-07] Response Shape Normalization**  
  Align backend responses with domain models (standardize `sender` vs `name`, `found_at` vs `created_at`, camelCase vs snake_case).
- [ ] **[WA-08] Lead Deep-Link from Activity Logs**  
  Include `lead_id` inside `/agent/logs` payload items so activity feed rows can directly navigate to lead threads.

### 🟢 Completed Milestones (Archive)
- [x] **[WA-M1] WhatsApp multi-device authentication & QR generation** (`start_agent.sh`)
- [x] **[WA-M2] Next.js Console layout & spec baseline** (`DASHBOARD_SPEC.md`)
- [x] **[WA-M3] Drafts read-only endpoint** `GET /api/drafts` added to `mvp.py`
- [x] **[WA-M4] Lead status update persistence** `PATCH /leads/{id}` with `LeadStatus` enum
- [x] **[WA-M5] Multi-tenant Supabase Schema definition** (`08-supabase-schema.md`)

---

## 🗂️ Component Sub-Pages
1. 🏗️ [[01 - WhatsApp Agent/WhatsApp Agent - Architecture & System Spec|System Architecture & DB Schemas]]
2. ⚙️ [[01 - WhatsApp Agent/WhatsApp Agent - Backend & API Roadmap|Backend API Tasks & Fixes]]
3. 🖥️ [[01 - WhatsApp Agent/WhatsApp Agent - Console & UI Tasks|Console Dashboard & Frontend Work]]
4. 🚀 [[01 - WhatsApp Agent/WhatsApp Agent - Deployment & Operations|Deployment, Daemons & Shell Scripts]]

---

## 💻 Fast Command Reference
```bash
# Start backend and agent
cd /Users/garvsanwariya/bounty/whatsapp_agent
./start_agent.sh

# Stop running services
./stop_agent.sh

# Run Next.js console
cd console && npm run dev

# Check agent logs in real-time
tail -f logs/agent.log
```
