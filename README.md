# KHM Institute — Website

A single-page, fully responsive corporate website for KHM Institute, with a
cinematic logo intro animation. Built as plain HTML/CSS/JavaScript — no
build step, no framework, no dependencies to install.

## What's in this project

```
├── index.html      ← the entire website (markup, styles, animation, logic)
├── vercel.json      ← deployment config for Vercel
└── README.md         ← this file
```

**Everything is self-contained in `index.html`:**
- All logo artwork (crown, letters, full lockup) is embedded directly in the
  file as base64-encoded images — nothing external to host or link to.
- All animation and interactivity (the cinematic intro, scroll reveals,
  mobile menu, nav behavior) is plain CSS + vanilla JavaScript in the same
  file.
- Typefaces (Fraunces, Inter) load from Google Fonts via a CDN `<link>` tag
  in `<head>` — this requires the visitor to have internet access, which is
  already assumed for any live website. No local font files are needed.

Because there's no build step, there is no `package.json` — this is not a
React/Next.js project, so nothing needs to be compiled or bundled. Vercel
will deploy it as a static site as-is.

## Deploy to Vercel

### Option A — Vercel CLI (fastest)
1. Install the CLI if you don't have it: `npm install -g vercel`
2. From inside this project folder, run:
   ```
   vercel
   ```
3. Follow the prompts (log in / create a project). When asked for the
   framework preset, choose **Other** — it will detect `index.html`
   automatically.
4. Run `vercel --prod` to push it live.

### Option B — Vercel Dashboard (no CLI)
1. Go to https://vercel.com/new
2. Choose **"Deploy without Git"** and drag-and-drop this whole folder
   (or the ZIP contents), **or** push this folder to a GitHub repo first
   and import that repo instead.
3. Framework preset: **Other**. Build command: none. Output directory:
   leave default (root).
4. Click **Deploy**.

Either way, once deployed you'll get a live `*.vercel.app` URL, and you can
attach your own domain (e.g. `www.khm.tn`) from the project's **Settings →
Domains** tab.

## Responsiveness

The layout has been tested at both desktop (1280px) and mobile (390px)
widths:
- Desktop: full horizontal nav, three-column value cards, horizontal value
  pillars.
- Mobile: hamburger navigation, single-column stacked cards and pillars,
  no horizontal scrolling.

## Notes / things you may still want to finish

- The **LinkedIn** and **Facebook** icons in the footer currently link to
  `#` placeholders — update the `href` values in `index.html` once you have
  the real profile URLs.
- The cinematic intro respects the visitor's OS-level "reduce motion"
  accessibility setting, and always includes a "Skip intro" button.

No design or content has been changed from the approved version — this
package is purely the same site, organized for deployment.
