<div align="center">

# Trace

**Paste your text. Set your speed. Let Trace do the typing.**

[![Chrome Web Store](https://img.shields.io/badge/Chrome%20Web%20Store-Available-4285F4?style=for-the-badge&logo=google-chrome&logoColor=white)](https://chromewebstore.google.com/detail/fcmocfafblllhjbpcbliedmpoklfgape)
[![Live Site](https://img.shields.io/badge/Live%20Site-trace--app--brown.vercel.app-black?style=for-the-badge&logo=vercel)](https://trace-app-brown.vercel.app)
[![Built with React](https://img.shields.io/badge/React-TypeScript-61DAFB?style=for-the-badge&logo=react)](https://react.dev)
![Visitors](https://visitor-badge.laobi.icu/badge?page_id=AsadGoharr.Trace&style=for-the-badge&color=1f6feb&labelColor=0d1117)

</div>

---

## What is Trace?

Trace is a Chrome extension that types text you have already written into web
editors, one keystroke at a time, at a speed you choose.

Paste does not always work. Some editors block it, some mangle formatting, some
lose your line breaks. Trace enters your text the way a keyboard would, and
pairs with a web dashboard for your drafts, deadlines, history and the monthly
leaderboard.

**What it is not:** Trace does not write anything for you, and a revision
history it produces is a record of typing rather than of composition. Where
work must be typed directly, or automated input is not allowed, Trace is not
the right tool — see the [ethics statement](https://trace-app-brown.vercel.app/ethics).

---

## Features

### Chrome Extension
- **Typing engine** — enters your text keystroke by keystroke at your chosen WPM
- **Pacing** — varies rhythm the way typing does: micro-pauses between words, hesitation at punctuation, slowdowns at the end of a sentence
- **Pre-flight check** — confirms there is somewhere for the keystrokes to land before it starts, rather than failing part-way
- **Pause, resume and recover** — stop mid-trace and pick up where you left off, even after closing the popup
- **Multi-platform** — Google Docs, Google Slides, Microsoft Word (web), Notion, Overleaf, Canvas LMS and 30+ other web editors

### Web Dashboard
- **Document history** — searchable log of every session with platform, word count and CSV export
- **Draft vault** — keep drafts and notes in one place
- **Deadlines** — set writing targets and track pace against them
- **Leaderboard** — global and friends-only rankings, with in-app friend requests
- **Profile** — public profile pages and display-name management

---

## Plans

**Free** — no word cap, no session cap.

- Unlimited words
- Full speed control, 30–100 WPM
- Human Touch Lite for an even rhythm
- Draft vault, deadlines and pacing
- File uploads (`.txt`, `.md`, `.csv`)
- Document history, leaderboard, keyboard shortcuts and notifications

**Trace Pro** — CAD $4.99/month. Everything in Free, plus:

- Full Human Touch engine — sentence and punctuation pauses, bursts, corrections and fatigue
- Your Fingerprint — Trace paces to your own measured rhythm
- Breaks on long documents — steps away between stretches instead of typing thousands of words unbroken

New accounts get **7 days of Pro free**, starting the first time the extension
is opened. The top three on the monthly leaderboard win 3, 2 and 1 days of Pro,
granted automatically on the 1st.

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
| Payments | Stripe |
| Hosting | Vercel (site), Chrome Web Store (extension) |
| Animations | Framer Motion |

---

## Project Structure

```
trace/
├── trace-extension/    # Chrome Manifest V3 extension (React popup)
├── trace-website/      # Marketing site + full user dashboard (React SPA)
└── supabase/           # Migrations and edge functions
```

---

## Architecture Overview

```
┌──────────────────┐        ┌──────────────────────┐
│ Chrome Extension │───────▶│  Supabase (DB/Auth)  │
│  (Manifest V3)   │        │  - traces            │
│  React + Vite    │        │  - user_profiles     │
└──────────────────┘        │  - leaderboard       │
                            │  - edge functions    │
┌──────────────────┐        └──────────┬───────────┘
│  Web Dashboard   │◀──────────────────┘
│  React SPA       │
│  Vercel          │
└──────────────────┘
```

The extension writes session data straight to Supabase. The dashboard reads the
same database, so activity shows up across every device. Scheduled edge
functions handle the monthly leaderboard reset and winner prizes.

---

## Links

- **Live site:** [https://trace-app-brown.vercel.app](https://tracetype.me/)
- **Chrome extension:** https://chromewebstore.google.com/detail/fcmocfafblllhjbpcbliedmpoklfgape
- **Changelog:** https://trace-app-brown.vercel.app/changelog
- **Ethics statement:** https://trace-app-brown.vercel.app/ethics

---

## Status

Actively developed. This repository holds the public documentation; the
application source is private.
