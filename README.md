# CompTrack - Tracks progress

A 30-day, advent-calendar-style study app for Third Year Computer Engineering students.
Each day unlocks a new topic with a short explanation, key points, a definition, an example,
a quick-revision note and a quiz. Covers AI, Computer Networks, Cloud Computing,
Data Privacy & Protection, and Theory of Computation.

**Live demo:** https://advikaaasingh19-lgtm.github.io/CompTrack/

## Features
- 30 sequentially unlocking study days with quizzes and instant scoring
- Streak tracking, overall progress and per-subject progress bars
- Analytics dashboard with custom-built SVG charts (accuracy over time, accuracy by subject)
- Weak-topic detector and revision queue that surfaces your lowest-scoring days first
- Installable PWA with a service worker for offline use
- Dark/light theme, topic search and subject filters
- All progress stored in the browser with `localStorage`. No login, no backend.

## Tech
Vanilla HTML, CSS and JavaScript. No framework, no build step, no runtime dependencies.

| File | Purpose |
|------|---------|
| `index.html` | App UI, logic and all 30 days of content |
| `manifest.json` | PWA install metadata |
| `sw.js` | Service worker for offline caching |
| `icon-192.png`, `icon-512.png` | App icons |

## Run locally
Open `index.html` in a browser. For the service worker and install prompt, serve it over
HTTPS or `localhost` (for example `python -m http.server`).

## Editing content
All study content lives in the `DATA` array in the `<script>` section of `index.html`.
Each entry holds the topic, explanation, key points, definition, example, quick-revision
line and quiz questions. Progress bars, unlock logic, charts and the revision queue all
read from that array.

## How it works
- **Unlocking:** day *n* opens once day *n−1* is marked complete.
- **Weak-topic detection:** every quiz attempt is logged with its score. The revision queue
  takes each day's most recent attempt and sorts by accuracy, lowest first.
- **Offline support:** `sw.js` caches responses and falls back to the cache when the network
  is unavailable.
