# LifeOS

A single-file personal operating system — a quiet dashboard for the whole of a life:
My Day, Tasks, Calendar, Money, Goals, Projects, People, Health, Learning, Career,
Documents, and an AI Studio agent fleet — all in one self-contained HTML app.

Live at **https://lifeopssys** (Vercel).

## What's here

| Path | Purpose |
|------|---------|
| `index.html` | The full app — self-contained (fonts, Chart.js, and all logic inline). Just open it. |
| `src/lifeos_override.js` | Runtime enhancement layer applied on top of the base app (2-col card lists, 7-level calendar, task domain picker, recurring tasks, agent fleet, AgentOS guide, Career Home, password gate). |
| `src/seed.json` | The seed state (schema 1) the app loads on first run. |

## Architecture (today)

- **Storage:** browser `localStorage` (key `lifeos.v1`). Export/import JSON from Settings.
- **Auth:** a client-side password gate (set on first use, stored as a SHA-256 hash). This is a
  privacy curtain, not server security — real per-user auth arrives with the Supabase step.
- **Agent surface:** `window.LifeOS.get() / .set() / .addTask() / .summary()` for assistants.

## Roadmap

- [ ] Supabase: per-user cloud sync of state + real auth
- [ ] Custom domain: LifeOpsSys
- [ ] Offline PWA install

## Local dev

Open `index.html` in any modern browser. No build step.
