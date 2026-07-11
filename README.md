# Six-Week Study Plan — Prelim Run

**10 Jul → 20 Aug 2026.** 36 study days · ~4 hrs/day · 6 days/week (rest Sunday) · ~22.8 hrs/week · 136.7 hours total.

Live dashboard: _(add your Vercel URL here after deploying)_

## Target

Prelim-realistic — a solid pass (C/B), where every cluster we drill is also a permanent A-level foundation.
Not chasing A's on everything.

**One cluster ≈ one day** (study sheet → test → gap cluster → re-test). This plan drills **25 load-bearing
clusters** and coverage-skims the rest. That's the design, not a shortfall.

## The Standard Cluster Cycle (the default 4-hour day)

| Time | Block |
|---|---|
| 60 min | Encode Cluster 1 — pre-study the chapter, take the first cluster, encode it |
| 60 min | Test — Claude generates an adversarial test from the cluster |
| 60 min | Encode Cluster 2 / cover the gaps — close the higher-order ones, then study the next cluster |
| 50 min | Test Cluster 2 + cover the gaps — re-test at a new angle |

## The 25 clusters

Maths 6 · Chemistry 7 · CSC 4 · Biology 5 · GP 3.

Gap clusters are **not** listed — they're generated live when a test exposes a weakness, and are
budgeted for in the 3rd/4th block and the five buffer days.

## How progress works

Ethan reports what he completed. Blocks get `"done": true` and a `"doneDate"` in `plan.js`, then pushed.
Vercel redeploys automatically.

Progress is **minutes-weighted**, not day-counted. `expected` = minutes scheduled on every study day up to
and including today (Sundays excluded). `delta = done − expected`.

## Files

- `index.html` — the whole dashboard. No build step, no dependencies.
- `plan.js` — the data. A single `window.PLAN` object. **The only file you need to edit.**

## Note on dates

10 Jul 2026 is a **Friday**. The source doc labelled it Thursday; weekday labels here are corrected against
the real 2026 calendar. The sequence and day numbers (1–36) are unchanged, and 10 Jul → 20 Aug is exactly
42 days minus 6 Sundays = 36 study days.

## Running locally

```bash
python3 -m http.server 8000   # http://localhost:8000
```
