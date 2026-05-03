# MissionControl-Secure — Replit Import Notes

## What This Project Is
Single-page mission control dashboard (neon green terminal aesthetic). Displays NYC Tailblazers squad/agent status. Mobile-first, PWA-ready.

## Stack Rules (non-negotiable)
- Static HTML/CSS/JS only — no framework required
- Deploy: Cloudflare Pages (never Vercel)
- No backend — data loaded from `data/` directory as JSON
- Auth (if added): simple token-based, no OAuth complexity

## Current State
- `index.html` — full dashboard UI (glitch header, squad cards, neon theme)
- `data/` — data directory (JSON config files)

## Improvements Roadmap
- [ ] Make data/ JSON files editable via admin panel (no code deploys for content changes)
- [ ] Add real-time status polling (fetch JSON on interval, update UI without reload)
- [ ] PWA manifest + service worker for offline/home screen install
- [ ] Password-protect the page (simple client-side PIN or Cloudflare Access)
- [ ] Dark/light mode toggle (keep neon as default)
- [ ] Mobile swipe gestures for card navigation

## Known Issues
- None logged — all static, no build step needed
