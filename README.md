# Tactus Website

A single-page product site for **Tactus — Automated Touchscreen Test Platform**,
ready to host free on GitHub Pages.

---

## What's here

```
index.html      The website (one page)
style.css       Styling
script.js       Small interactions (nav, scroll reveal)
assets/         Images, logo, favicons
.nojekyll       Tells GitHub Pages to serve files as-is
```

---

## Publish it on GitHub Pages (free)

1. Create a new GitHub repository (for a personal site, name it
   `yourusername.github.io`; for a project site, any name works).
2. Upload **everything in this folder** (index.html, style.css, script.js,
   the `assets/` folder, and `.nojekyll`) to the repo — keep the structure.
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Pick the **main** branch and the **/(root)** folder, then **Save**.
6. Wait ~1 minute. Your site is live at the URL shown on that Pages screen
   (e.g. `https://yourusername.github.io/` or `.../reponame/`).

That's it. Every time you push changes, the site updates automatically.

---

## Two things to fill in

Search `index.html` for `TODO` — there are two spots:

### 1. Your app download link
Find the button with `id="dmgLink"` and set its `href` to wherever you host
the Tactus `.dmg`:

```html
<a href="https://your-download-url/Tactus-2.15.dmg" ... id="dmgLink">
```

**Easiest way to host the .dmg on GitHub:** create a **Release** in your repo
and attach the `.dmg` as a release asset, then use that asset's download URL.
(Releases are better than committing large binaries into the repo.)

Also update the version pills (`id="appVersion"` and the text `v2.15`) when you
ship a new version, so visitors always see the current number.

### 2. The Operator's Manual PDF
The manual section embeds a file named exactly:

```
TACTUS_Operator_Manual.pdf
```

When you're ready, **drop that PDF into this same folder** (next to
`index.html`) and upload it. The embed and the "Open in new tab" button start
working automatically. Until then, a friendly placeholder is shown.

> Tip: export the PDF from the Word manual (`Tactus_Operator_Manual.docx`)
> via **File → Save As / Export → PDF**, name it `TACTUS_Operator_Manual.pdf`,
> and place it here.

---

## The serial driver link (already set)

The download section links to the **official WCH CH34x macOS driver** —
the free, trusted driver for the machine's CH340 USB-to-serial chip:

- Official page: https://www.wch-ic.com/downloads/CH34XSER_MAC_ZIP.html
- Universal binary (Apple Silicon + Intel), macOS 10.9–15
- A Homebrew option is also shown for advanced users:
  `brew install --cask wch-ch34x-usb-serial-driver`

You don't need to change anything here unless you'd prefer to host the driver
yourself.

---

## Customizing

- **Colors / fonts:** edit the `:root` variables at the top of `style.css`.
- **Text:** all copy is plain text in `index.html`.
- **Images:** replace files in `assets/` (keep the same names), or add your own
  and update the `src` in `index.html`.
- **Custom domain:** add a `CNAME` file with your domain and configure it in
  Settings → Pages.

---

© Akhil R. Pathapati
