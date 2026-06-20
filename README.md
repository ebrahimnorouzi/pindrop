# 📍 PinDrop Challenge

A single-page web app for the **[PinDrop Challenge](https://youtube.com/@pindrop-challenge)** YouTube channel.

Every day it gives you **one** random "drop" — a mystery coordinate within reach of where
you are. Go find out what's there, film it, post it. The point is **pinned for the whole
day**, so a reload shows the same target; a fresh one is drawn at local midnight.

> 🌐 Light theme · 🌍 Bilingual **English / فارسی** (with full RTL) · 📱 Works great on phones · 🔐 No API keys, no backend.

## ✨ Features
- **One drop a day**, deterministically seeded from the date — reproducible even if storage is cleared.
- Shows **coordinates, distance, bearing + compass** and a clean light Leaflet map (CARTO tiles) with the radius ring.
- One-tap links to **Directions / Google Maps / OpenStreetMap**, plus a **Share** button (Web Share API → clipboard fallback) for video intros.
- **GPS with graceful fallback**: denied location? Enter coordinates manually or use a fallback city.
- **Language toggle** (EN ⇄ فارسی) with Persian numerals and right-to-left layout; choice is remembered.
- Links straight to the channel's **YouTube** and **Instagram**.
- Accessible: visible focus styles, `prefers-reduced-motion` respected, strong contrast.

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
The only external dependencies are **Leaflet** (via cdnjs) and **CARTO** map tiles.

## 🧭 Backlog / ideas
- "Water only" / "land only" filter for the drop.
- Exclude-roads / "properly wild" mode.
- Auto-generated shareable drop-card image for video intros.
- Optional live re-anchor mode (always X km from your current position — no fixed target).

---
Built for the PinDrop Challenge · drops are random & for fun — explore safely and respect private property.
