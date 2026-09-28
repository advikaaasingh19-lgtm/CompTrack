# Tech Dussehra — 30 Days of Third Year Computer Engineering

A Dussehra-themed advent-calendar study app covering AI, Computer Networks, Cloud Computing,
Data Privacy & Protection, and Theory of Computation. Single self-contained HTML file — no
build step, no backend, no dependencies to install.

## Features
- 30-day unlockable study calendar with per-day explanations, key points, and quizzes
- Streak tracking, overall + subject-wise progress bars
- Analytics dashboard (Chart.js) — accuracy over time, accuracy by subject
- Weak-topic detector + revision queue (surfaces your lowest-scoring days first)
- Dark/light mode, search + subject filters, reset with confirmation
- PWA-ready: web app manifest + offline-caching service worker
- All progress stored in the browser via `localStorage` — no login, no server

## Run it locally
Just open `index.html` in a browser. That's it.

## Deploy on GitHub Pages (free hosting + working PWA install)
1. Create a new GitHub repo, e.g. `tech-dussehra`.
2. Add `index.html` (rename the file to exactly `index.html`) to the repo root and push.
3. In the repo: **Settings → Pages → Source** → select the `main` branch, `/ (root)` folder → **Save**.
4. GitHub gives you a live URL like `https://<your-username>.github.io/tech-dussehra/`.
5. Because it's now served over real HTTPS from your own domain (not a preview iframe),
   the "Add to Home Screen" / install prompt and offline caching will actually work —
   they're disabled inside sandboxed previews by design.

## Editing content
All 30 days live in the `DATA` array near the top of the `<script>` tag in `index.html`.
Each entry is one object: topic, explanation, key points, definition, example, quick-revision
line, and quiz questions. Add, edit, or reorder entries there — everything else (unlock logic,
progress bars, charts, revision queue) reads from that array automatically.

## Tech notes
- Vanilla HTML/CSS/JS — chosen over a React build so it needs zero tooling to host or hand in.
- Chart.js loaded via CDN (cdnjs) for the analytics dashboard.
- Fonts: Fraunces (headings) + JetBrains Mono (labels) via Google Fonts.
