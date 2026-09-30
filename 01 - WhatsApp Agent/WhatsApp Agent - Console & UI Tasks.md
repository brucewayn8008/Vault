# 🖥️ WhatsApp Agent — Console & UI Tasks

> **Path:** `whatsapp_agent/console/`  
> **Framework:** Next.js (App Router), Tailwind CSS, shadcn/ui, TanStack Query

---

## 📋 Console Frontend Task Board

### 📊 Overview & Dashboard Views
- [ ] **QR Code Reconnection Widget:** Auto-refresh QR code poll with graceful timeout and countdown timer.
- [ ] **Live Metrics Cards:** Active Leads, Hot Leads, Response Rate, Daily Quota Meter.
- [ ] **Activity Feed Stream:** Implement cursor-based infinite scroll connected to new paginated `/agent/logs`.

### 🗂️ Lead Pipeline & CRM Board
- [x] Kanban board drag-and-drop status update (`PATCH /leads/{id}`).
- [ ] Fast filter bar by Status, Needs Response, Group Source.
- [ ] Search input with 300ms debounce.
- [ ] Lead detail sheet: display message history, AI summary, lead qualification notes, and one-click WhatsApp web link.

### 📝 Drafts Approval Queue
- [x] Draft count badge in sidebar navigation.
- [ ] Quick approve button (`Cmd+Enter` shortcut).
- [ ] Quick edit input before sending.
- [ ] Discard draft with optimistic UI removal.

### ⚙️ Settings & Agent Tuning
- [ ] Prompt editor with variable syntax highlighting (`{brand_name}`, `{services}`, `{booking_link}`).
- [ ] Working hours & schedule configuration for group promotions.
- [ ] Daily message throttle limiter.

---

## 🔗 Quick Links
- [[01 - WhatsApp Agent/WhatsApp Agent - Master Task Hub|WhatsApp Agent Task Board]]
- [[01 - WhatsApp Agent/WhatsApp Agent - Backend & API Roadmap|Backend Endpoints Spec]]
