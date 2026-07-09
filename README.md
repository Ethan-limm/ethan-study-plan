# A-Level Prelim Run-In — public study tracker

A 39-day, 156-hour study plan for Ethan Lim, reverse-engineered backwards from the **18 Aug 2026** prelim date.
Live dashboard: _(add your Vercel URL here after deploying)_

## The premise

Prelims are treated as a **diagnostic**, not a target. The real exam is the November 2026 A-Levels.
Hours are allocated by measured score gap, not by which subject feels worst.

| Subject | Standing | Hours | Why |
|---|---|---|---|
| Mathematics 9758 H2 | U | 50 | Lowest grade *and* fastest marks-per-hour. The only subject that fully closes inside the budget. |
| Chemistry 9729 H2 | D/E | 36 | Calculation backbone + the reasoning templates that recur verbatim across topics. |
| China Studies 9629 H2 | D/E | 26 | Economy is the likely P2 compulsory. Cross-Topic Bridge is the 18→19 wall. |
| General Paper 8881 H1 | C/B | 16 | Already near target. Skills, not content. |
| Biology 9744 H2 | B/C (unverified) | 14 | Day 1 is a timed paper to test the "I can smoke through it" claim. |
| Convergence | — | 14 | Official past papers, timed. The only real readiness gate. |

**156 hours cannot cover a ~247-cluster syllabus.** What gets cut is listed explicitly on the dashboard.
Spreading thin and closing nothing is the failure mode this plan is designed to avoid.

## How progress works

Ethan reports what he actually completed. Completed blocks get `"done": true` and a `"doneDate"`
written into `plan.js`, then pushed. Vercel redeploys automatically.

Progress is **hours-weighted, not task-counted** — a 4-hour timed paper counts more than a 2-hour block.
`expected` = hours scheduled on every day up to and including today. `delta = done − expected`.
Negative delta past 12 hours flips the banner red, because that is three full study days lost.

## Files

- `index.html` — the whole dashboard. No build step, no dependencies, no framework.
- `plan.js` — the data. A single `window.PLAN` object. **This is the only file you need to edit.**

## Editing

Fork, edit `plan.js`, open a PR. To mark a block complete:

```js
{"subject":"maths","label":"Vectors — Lines & Planes (1/2)","hours":2,
 "done":true,"doneDate":"2026-07-13"}
```

To change the plan itself, edit the `days` array. The dashboard recomputes every number from the data —
nothing is hardcoded.

## Running locally

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

Or just open `index.html` directly — `plan.js` is a plain script, so there is no CORS problem.
