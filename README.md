# Dozzaa — Deployment Guide

Your app is one self-contained folder: `index.html` + `manifest.json` + `sw.js` + `icons/`.
No build step, no server, no database — works directly on GitHub Pages and installs on Android like a real app.

## 1. Push to your existing repo

You already have `dozzerbobo/Dozzaa-Demo-` live at `https://dozzerbobo.github.io/Dozzaa-Demo-/`.

```bash
# from inside your cloned dozzerbobo/Dozzaa-Demo- repo
cp -r path/to/dozzaa-app/* .
git add .
git commit -m "Dozzaa v2: full ad platform demo, installable PWA"
git push
```

Wait 1–2 minutes for GitHub Pages to redeploy, then visit your existing URL.

## 2. Install on Android

1. Open `https://dozzerbobo.github.io/Dozzaa-Demo-/` in **Chrome** on an Android phone.
2. Tap the **⋮** menu → **"Install app"** (or **"Add to Home screen"**).
3. Confirm. Dozzaa now opens full-screen from your home screen, with your logo as the icon — no browser bar, works offline after first load.

(There's also an in-app **Settings → Install App** tab with the same instructions, plus a direct install button if Chrome's install prompt is available.)

## 3. Demo login

```
Email:    demo@dozzaa.ng
Password: demo1234
```

All data (campaigns, analytics, ad copy, etc.) is seeded into the browser's local storage on first load — fully interactive, resets if the person clears site data or uses a different device/browser.

## What's inside

- **Overview** — spend/impressions/ROAS stats, performance trend, platform spend pie chart, AI recommendation cards, live campaigns table
- **Campaigns** — full create/edit/delete/pause, search, filter by platform & status
- **Analytics** — date-range + platform filters, spend & conversion trend charts, per-platform comparison
- **Budget Optimizer** — drag sliders to reallocate budget across Meta/Google/TikTok/X, auto-optimize toggle
- **Social Feed & Boost** — organic posts feed, one-tap "Boost" with budget/duration/objective
- **AI Creative Tools** — generates ad copy in **English, Pidgin, Yorùbá, Igbo, and Hausa** per platform, save to a library, approve flow
- **Geo Targeting** — Nigeria state-by-state performance breakdown with drill-in detail
- **Settings** — profile, connected platforms (Meta/Google/TikTok/X toggle), notifications, billing, install instructions

## Notes

- This is a **frontend demo**: data lives in the browser (`localStorage`), not a real backend. It's built to look and behave like the real product for demos, pitches, and investor walkthroughs.
- Two stock photo URLs (Pexels) are used for sample social posts — they need general internet access to load (works fine on a real device/GitHub Pages; just gracefully hides if blocked).
- If you ever want this wired to a real backend (Postgres + your actual Meta/Google/TikTok/X APIs + Paystack billing), the original Next.js source you uploaded is the right starting point for that — happy to help adapt it when you're ready for that step.
