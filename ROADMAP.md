# MLB Brain · Roadmap & Future Requests

> Tracked here in priority order. Move items to **Done** when shipped.
> Last updated: July 29, 2026

---

## 🔴 High priority

### API key session memory
Replace Anthropic API key storage from `localStorage` to a session-only in-memory variable. On each visit, the user is prompted to enter the key once. It lives in memory for the session and is discarded when the tab closes — never written to disk or storage.

**Approach:** Option 2 — prompt on use, never store. Keep GitHub token in `localStorage` (needs to persist). Only the Anthropic key moves to in-memory.

---

## 🟡 Medium priority

### Multi-user login system
As the site grows beyond a single user, replace the shared password with individual accounts.

**Requirements:**
- Individual user accounts (email + password or OAuth)
- Per-user settings and API keys
- Role-based access — Admin vs Read-only viewer
- Session management with expiry
- Admin panel to manage users, set subscription expiry dates, suspend/activate accounts

**Approach:** Supabase (free tier Postgres + auth + row-level security). Admin panel as a separate protected page. Existing dashboard gets an auth gate on load.

---

### Admin panel — user & subscription management
Companion to the multi-user login system above. A dedicated admin-only page to:

- View all registered users
- Add / remove users
- Set subscription expiry dates per user
- Toggle active / suspended status
- View last login and usage activity

**Depends on:** Multi-user login system being in place first.

---

## 🟢 Low priority / future exploration

### Closing line value (CLV) tracking
Add a manual CLV field to each pick in the brain file. Log the odds at pick time vs the closing line. Track CLV average over time as a model health metric — a positive CLV average confirms real edge independent of win/loss variance.

**Why:** Win/loss records over short samples are noisy. CLV is the gold standard for whether a model has genuine edge.

---

### Automatic probable pitcher data
Pull confirmed starters automatically from the ESPN or MLB API on page load and inject them into the picks context, removing the need to paste slate info manually.

---

### Push notifications
Send a notification when auto-update fires (all games final, brain updated). Useful when the tab is in the background. Web Push API via a lightweight service worker.

---

### Pick confidence history chart
Track confidence score per pick over time. Visualise whether high-confidence picks are outperforming low-confidence ones — validates the 6/10 minimum threshold or suggests adjusting it.

---

### Mobile app (PWA)
Wrap the existing dashboard as a Progressive Web App so it can be installed on iOS/Android home screens. Requires a service worker and a `manifest.json`. No native code needed — the existing HTML is the app.

---

## ✅ Done

| Feature | Shipped |
|---|---|
| Single HTML dashboard hosted on GitHub Pages | Jul 2026 |
| GitHub API brain file sync (pull + push) | Jul 2026 |
| Anthropic API streaming picks analysis | Jul 2026 |
| Live ESPN slate with auto-polling every 90s | Jul 2026 |
| Auto-update brain when picked games go final | Jul 2026 |
| Analytics page — KPIs, charts, insights, ledger | Jul 2026 |
| Period filters (7 days, month, week, today, all time) | Jul 2026 |
| Password-gated Settings page | Jul 2026 |
| Full cross-browser and mobile responsive layout | Jul 2026 |
| Cache-control headers to prevent stale deploys | Jul 2026 |
| Custom domain — mlb.beclutch.me | Jul 2026 |
| Onboarding step flow for first-time users | Jul 2026 |
| Reduced motion support | Jul 2026 |
| iOS safe area inset handling | Jul 2026 |
