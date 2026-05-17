# Cabri Caldwell — Brand OS

A single-page brand operating system for Cabri Caldwell's five-brand portfolio:
**Minimize then Organize**, **Remove LBK**, **Ironclad**, **Organizer Near Me**, and **Pro Organizer Studio**.

Built on the Brand → Messaging → Activate → Convert → Automate framework. Brand
foundations are sourced from Cabri's Notion portal and embedded into this hub for
at-a-glance reference, with deeplinks back to the source-of-truth Notion pages.

## What's in this repo

| File | Purpose |
|------|---------|
| `index.html` | The entire Brand OS — self-contained, no build step, no dependencies |
| `vercel.json` | Vercel config (clean URLs, cache headers) |
| `README.md` | This file |
| `.gitignore` | Standard ignores |

## How to deploy

### Option A — Connect this repo to Vercel (recommended for ongoing updates)

1. Push this repo to GitHub.
2. Go to [vercel.com/new](https://vercel.com/new) and import the repo.
3. Framework preset: **Other**. Build command: *(leave empty)*. Output directory: *(leave empty)*.
4. Click **Deploy**. Every future push to `main` auto-deploys.

### Option B — Drag-and-drop (no Git)

1. Go to [vercel.com/new](https://vercel.com/new).
2. Drag this entire folder onto the page.
3. Click **Deploy**.

## How to update brand content

All brand content lives in a single `BRAND_CONTENT` object inside `index.html`.
Search for `const BRAND_CONTENT = {` and edit the keys for each brand:

```js
const BRAND_CONTENT = {
  mto:      { essence, positioning, mission, audiencePrimary, values, ... },
  remove:   { ... },
  ironclad: { ... },
  onm:      { ... },
  studio:   { ... },
};
```

Each brand's `notionUrl` should point to the canonical Brand Foundation page in
Notion so the hub stays linked to the working source-of-truth.

Brands themselves (name, industry, stage) live in `CLIENT_CONFIG.brands` higher up.

## Local preview

No build step. Just open `index.html` in a browser, or run any static server:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

---

Built by Bailey Armendarez · Arch Ann
