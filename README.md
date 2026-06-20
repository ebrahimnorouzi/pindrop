# 📍 PinDrop Challenge

A single-page web app for the **[PinDrop Challenge](https://youtube.com/@pindrop-challenge)** YouTube channel.

Every day it gives you **one** random "drop" — a mystery coordinate within reach of where
you are. Go find out what's there, film it, post it. The point is **pinned for the whole
day**, so a reload shows the same target; a fresh one is drawn at local midnight.

> 🌐 Light **&** dark theme · 🌍 Bilingual **English / فارسی** (with full RTL) · 📱 Installable PWA · 🔐 No API keys, no backend.

## ✨ Features
- **One drop a day**, deterministically seeded from the date — reproducible even if storage is cleared, pinned until local midnight.
- **Coordinates, distance, bearing + compass** on a Leaflet map with the radius ring, "you are here" marker, and a line to the target.
- **Map style switcher** — Light / Dark / Satellite (CARTO + Esri tiles, no key).
- **🧲 Live compass navigation** — uses the device's orientation sensor to point a needle at today's drop with "turn left/right" guidance (great while filming on location).
- **🖼️ Shareable drop-card generator** — renders a branded 1080×1080 image (coords, distance, bearing, mini-compass, Drop No., date, channel handle) you can **download or share** straight into a video intro / story.
- **📊 Expedition log** — day-streak counter, total drops, total distance, and your recent drops with quick map links.
- **⏱️ Live countdown** to the next drop; auto-refreshes at midnight.
- **⚙️ Settings** — adjustable drop **radius**, **km/mi** units, theme, and language; all saved on-device.
- **GPS with graceful fallback**: denied location? Enter coordinates manually or use a fallback city.
- **Light / Dark / Auto theme** that follows the system, plus a one-tap toggle. **Persian numerals** and RTL throughout.
- **Copy coordinates**, one-tap **Directions / Google Maps / OpenStreetMap**, native **Share** (Web Share API → clipboard fallback).
- Links straight to the channel's **YouTube** and **Instagram**.
- **Installable** (PWA manifest) and **accessible**: visible focus styles, `prefers-reduced-motion` respected, strong contrast.

## 🛠️ Configure
Everything tweakable lives in the `CONFIG` object at the top of the `<script>` in `index.html`:

| Key | What it does |
| --- | --- |
| `RADIUS_KM` | How far a drop can land from you (default `100`). |
| `EPOCH` | Launch date — the "Drop No." counter starts at 1 here. |
| `SEED_SALT` | Change to globally reshuffle the daily sequence. |
| `FALLBACK_ORIGIN` | Origin used when GPS is denied (default: Tehran). |
| `SOCIAL.youtube` / `SOCIAL.instagram` | Channel links shown across the page. |

## 🚀 Deploy (GitHub Pages)
1. Push to `main`.
2. **Settings → Pages → Deploy from branch → `main` / root**.
3. Live at `https://<user>.github.io/pindrop/`.

> ⚠️ GPS requires **HTTPS** — test the location flow on the deployed Pages URL, not a local `file://` open.

## 📦 Constraints
Single self-contained `index.html`: no build step, no backend, no framework, no bundler.
External dependencies are **Leaflet** (via cdnjs), **CARTO** + **Esri** map tiles, and **Google Fonts**
(Inter / Vazirmatn) — the fonts degrade gracefully to system fonts if blocked.

## 🧭 Backlog / ideas
- "Water only" / "land only" filter for the drop.
- Exclude-roads / "properly wild" mode.
- Optional live re-anchor mode (always X km from your current position — no fixed target).
- Offline support via a service worker (needs a second file, so it's intentionally left out for now).

---
Built for the PinDrop Challenge · drops are random & for fun — explore safely and respect private property.
