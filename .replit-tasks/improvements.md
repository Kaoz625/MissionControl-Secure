# Replit Agent Task: MissionControl-Secure

## Goal
Upgrade MissionControl-Secure from its current terminal-green aesthetic to a modern dark-mode command center UI, update the Claude model reference from any legacy version to claude-sonnet-4-6, and improve the inbox/message UI for real usability.

## Tasks
1. **Model update**: search all JS in index.html and the data/ folder for any hardcoded Claude model strings (e.g., "claude-3-sonnet", "claude-3-opus", "claude-3-haiku", "claude-sonnet-3-5") and replace with "claude-sonnet-4-6"; also update any model display labels in the UI
2. **Inbox UI redesign**: the current squad-card layout is functional but bare — redesign the message cards with: sender avatar (initials circle), message preview (first 80 chars), timestamp in relative format ("2 min ago"), unread count badge, priority indicator (color-coded left border: red=urgent, yellow=normal, gray=read); keep the neon-green accent but use it sparingly as a highlight only
3. **Add dark mode toggle**: add a sun/moon button in the top-right that switches between the current terminal-dark theme and a softer dark mode (#1a1a2e background, #e0e0e0 text, blue accent #4a9eff) — persist preference in localStorage
4. **Inbox data structure** (data/inbox.json): if it exists, read the current schema and add 5 realistic test messages with varied priorities, timestamps, and senders (Claude agents: nyc-admin, nyc-tech, nyc-main, nyc-info, nyc-owner); if it doesn't exist, create it with this schema: `[{id, from, subject, preview, body, timestamp, priority, read}]`
5. **Message detail view**: clicking a squad card should expand it (or open a modal) showing the full message body, a "Mark as Read" button, and a "Reply" textarea that logs to console (no backend needed); add a smooth CSS transition for open/close
6. **Search/filter bar**: add a search input at the top of the inbox that filters cards by sender name or message content in real-time (JS filter on keyup); add filter chips for priority (All / Urgent / Normal / Read)
7. **Status bar**: at the top below the "Mission Control" header, show a live clock (JS setInterval), the current date, and a "SECURE" status indicator with a pulsing green dot
8. **Mobile improvements**: the current layout is already mobile-focused; ensure the new features (modal, filter bar, status bar) are all touch-friendly with 44px minimum tap targets
9. **Performance**: the entire app is one HTML file — keep it that way but split JS into a `<script>` section at the bottom; remove any redundant inline styles that are duplicated in the `<style>` block

## Tech Stack
- Vanilla HTML5 / CSS3 / JavaScript (single-file app — do not convert to a framework)
- LocalStorage for dark mode preference and read/unread state
- JSON data from data/inbox.json (fetched with fetch() or embedded in script)

## Deploy Target
Cloudflare Pages (static). Never Vercel.

## Done When
- [ ] All Claude model references updated to "claude-sonnet-4-6"
- [ ] Inbox cards show avatar, preview, timestamp, unread badge, and priority border
- [ ] Dark mode toggle works and persists across page reloads
- [ ] data/inbox.json has at least 5 realistic test messages
- [ ] Clicking a card expands/opens a detail view with full message body
- [ ] Search bar filters cards in real-time
- [ ] Priority filter chips (All / Urgent / Normal / Read) work
- [ ] Status bar shows live clock and date
- [ ] No console errors on load
