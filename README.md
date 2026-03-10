<div align="center">

# Trace

**Paste your text. Set your speed. Let Trace do the typing.**

[![Chrome Web Store](https://img.shields.io/badge/Chrome%20Web%20Store-Available-4285F4?style=for-the-badge&logo=google-chrome&logoColor=white)](https://chromewebstore.google.com/detail/fcmocfafblllhjbpcbliedmpoklfgape)
[![Live Site](https://img.shields.io/badge/Live%20Site-trace--app--brown.vercel.app-black?style=for-the-badge&logo=vercel)](https://trace-app-brown.vercel.app)
[![Built with React](https://img.shields.io/badge/React-TypeScript-61DAFB?style=for-the-badge&logo=react)](https://react.dev)

</div>

---

## What is Trace?

Trace is a Chrome extension that automatically types out your text on popular writing platforms — at a natural, human-like speed you control. Pair it with the web dashboard to track your productivity, compete on the leaderboard, and manage writing deadlines — all in one place.

---

## Features

### Chrome Extension
- **Auto-typing engine** — pastes and types your text keystroke-by-keystroke at your chosen WPM
- **Human Engine** — randomizes timing, introduces micro-pauses, and simulates natural typing rhythm to make output look authentic
- **Multi-platform support** — works on Google Docs, Google Slides, Microsoft Word (web), Notion, Overleaf, and Canvas LMS
- **Session persistence** — resume a trace where you left off even after closing the popup

### Web Dashboard
- **Analytics** — WPM trend chart, activity heatmap, words-per-month counter
- **Document History** — searchable log of every session with platform, word count, and CSV export
- **Leaderboard** — compete with friends; in-app friend requests and ranking system
- **Deadlines** — set writing targets with urgency levels and track progress
- **Profile** — public profile pages, username management, upgrade to Pro

### Pricing
- **Trace Basic** — Free: 2,500 words/month, 5 sessions/day, 50 WPM, Human Touch Lite
- **Trace Pro (Student)** — $4.99/mo, $14.99/semester, or $39.99/yr
- **Trace Pro (Professional)** — $9.99/mo or $79.99/yr
- **Founding Member** — $89 one-time (lifetime access)

Pro unlocks unlimited words & sessions, full Human Touch Engine, full speed control (30–100+ WPM), saved drafts, analytics, deadlines, and AI features (coming soon).

---

## Supported Platforms

| Platform | Status |
|---|---|
| Google Docs | ✅ Supported |
| Google Slides | ✅ Supported |
| Microsoft Word (web) | ✅ Supported |
| Notion | ✅ Supported |
| Overleaf | ✅ Supported |
| Canvas LMS | ✅ Supported |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend (site + extension) | React 19, TypeScript, Vite 7 |
| Styling | Tailwind CSS v4 |
| Backend / Auth / DB | Supabase (PostgreSQL + Auth + Realtime + Edge Functions) |
| Payments | Stripe (Payment Links + Webhooks) |
| Hosting | Vercel (site), Chrome Web Store (extension) |
| Animations | Framer Motion, Three.js |

---

## Project Structure

```
trace/
├── trace-extension/    # Chrome Manifest V3 extension (React popup)
└── trace-website/      # Marketing site + full user dashboard (React SPA)
```

---

## Architecture Overview

```
┌─────────────────┐        ┌─────────────────────┐
│  Chrome Extension│──────▶│   Supabase (DB/Auth) │
│  (Manifest V3)   │        │  - sessions table    │
│  React + Vite    │        │  - profiles table    │
└─────────────────┘        │  - leaderboard table │
                            └──────────┬──────────┘
┌─────────────────┐                   │
│  Web Dashboard  │◀──────────────────┘
│  React SPA      │
│  Vercel         │
└─────────────────┘
```

The extension writes typing session data directly to Supabase. The dashboard reads from the same database, giving users a real-time view of their activity across all sessions and devices.

---

## Links

- **Live site:** https://trace-app-brown.vercel.app
- **Chrome extension:** https://chromewebstore.google.com/detail/fcmocfafblllhjbpcbliedmpoklfgape

---

## Status

Actively developed. The source code is private, but the extension and site are publicly available.

---

<div align="center">
  <sub>Built by <a href="https://github.com/AsadGoharr">AsadGoharr</a></sub>
</div>
