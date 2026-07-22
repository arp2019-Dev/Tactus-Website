<h1 align="center">Tactus</h1>
<p align="center"><b>A machine that taps your screen for you.</b></p>
<p align="center">Automated touchscreen testing on real iPads, iPhones, and tablets.</p>

---

This repository hosts the **Tactus website** — the product page, the macOS app
download, and the operator's manual. It's served with GitHub Pages.

**Live site:** https://arp2019-dev.github.io/Tactus-Website/

---

## What is Tactus?

Tactus is a small robot that runs touch tests on a real device. You mount an
iPad or phone in the frame, draw the taps and swipes you want on a live camera
view, and press play. It performs the same sequence on the actual hardware,
the same way every time — useful for repeat testing, long soak tests, demos, or
anything where you'd otherwise be poking a screen by hand.

It does six kinds of touch — tap, double tap, tap and hold, swipe, drag/scroll,
and move — each tuned so the screen registers it like a real finger. A 4K
overhead camera shows you the screen, and a one-time calibration makes taps land
exactly where you click.

- **Motion:** custom CoreXY gantry, 241 x 154 mm work area
- **Toolhead:** stepper-driven cam with a spring-loaded rubber stylus
- **Vision:** IMX415 4K USB camera
- **Control:** ZNP Robin Nano V1.3 running Marlin
- **App:** gesture-first macOS app (Python / PySide6)

---

## Download

Get the latest macOS app from the website's **Download** section, or straight
from [Releases](../../releases).

The app needs a free USB serial driver (for the board's CH340 chip). The
download page links to the official WCH driver and explains the install. The
current app version always shows in the app's title bar and top-right toolbar.

---

## Repository structure

```
index.html                     The website (single page)
style.css                      Styles
script.js                      Nav + small interactions
TACTUS_Operator_Manual.pdf     The manual (embedded on the site)
.nojekyll                      Serve files as-is on GitHub Pages
assets/                        Images, logo, favicons
  dev_*.png                    Product photos (transparent)
  annot_*.jpg, app_*.jpg       Annotated app screenshots
  flow_startup.jpg             Startup flow diagram
  logo_mark.png, favicon_*     Branding
```

The app source code and the DMG build kit live separately; this repo is just the
public website and its assets.

---

## Updating

### Ship a new app version
1. Build the new `Tactus-<version>.dmg`.
2. Create a GitHub **Release** (e.g. tag `TACTUS-V2.16`) and attach the `.dmg`.
3. In `index.html`, update the download link's `href` to the new release asset
   URL, and bump the two version labels (`id="appVersion"` and the `Tactus v2.15`
   text near the bottom of the Download section).
4. Commit and push — Pages redeploys automatically.

### Update the manual
Replace `TACTUS_Operator_Manual.pdf` in the repo root (keep the same filename)
and push. The embedded viewer and the "Open in new tab" link pick it up
automatically.

### Edit the site
- Copy is plain text in `index.html`.
- Colors and fonts are CSS variables at the top of `style.css`.
- Product images live in `assets/` — replace a file with the same name to swap
  it, or add new ones and update the `src` in `index.html`.

---

## Hosting (GitHub Pages)

This repo is already set up for Pages. If you fork or re-create it:

1. **Settings -> Pages**
2. **Source:** Deploy from a branch
3. **Branch:** `main`, folder `/(root)` -> Save
4. The live URL appears on that screen after ~1 minute.

To use a custom domain, add a `CNAME` file with your domain and configure it in
Settings -> Pages.

---

<p align="center">(c) Akhil R. Pathapati</p>
