# knowable.laboracollective.com

Standalone microsite for **What Is Knowable** — the mental-model umbrella for
Yamicia Connor / Labora Collective's three-track campaign through the midterms.

## What's here

- `index.html` — the entire site. Single long-scroll page, inline CSS, no build step.
- `netlify.toml` — publish-from-root config.
- `robots.txt` — allow all.

## Deploy

Two options.

### Option A — separate Netlify site, this repo as source

1. Create a new Netlify site.
2. Point it at this repo (`yconnor-maker/laboracollective`).
3. Set **base directory** to `knowable-site/`.
4. Set **publish directory** to `knowable-site/`.
5. No build command needed (static).
6. Add custom domain `knowable.laboracollective.com` and let Netlify provision the cert.

### Option B — move to its own repo

```
mkdir ../knowable
cp -r ./* ../knowable/
cd ../knowable
git init && git add . && git commit -m "Initial commit"
gh repo create yconnor-maker/knowable --public --source=. --push
```

Then point Netlify at the new repo with publish dir `.`.

## Style

Matches the **Manufactured Healthcare Crisis** style — espresso (`#362511`) +
gold (`#9E7D0A`), Cormorant Garamond display, EB Garamond body, DM Sans UI.
Self-contained — does not depend on `lc-standard.css`.

## Tracks linked

| Track | Status | Link |
|---|---|---|
| Manufactured Healthcare Crisis | Live | `laboracollective.com/intelligence/labora-rounds/manufactured-healthcare-crisis/` |
| Bring The Bolt Cutters | Launching May 29 | — |
| Crisis to Care | Launching soon | — |

## Email capture

Both capture forms POST to the Beehiiv subscriptions endpoint:
`https://api.beehiiv.com/v2/publications/laboracollective/subscriptions`.
Verify the publication slug matches the live LC newsletter before going live.
