# OLDMILL.in

Landing site for the OLDMILL project house. Plain HTML/CSS/JS, no build step, no dependencies except Google Fonts.

## Structure

```
index.html            → oldmill.in
about/index.html       → oldmill.in/about
rabbithole/index.html  → oldmill.in/rabbithole
archive/index.html     → oldmill.in/archive
CNAME                  → custom domain config for GitHub Pages
```

Each folder maps to a clean URL because GitHub Pages serves `index.html` for a directory automatically — `oldmill.in/archive` resolves to `archive/index.html` with no extra config.

## Notes

- The homepage wordmark ("OLDMILL.in") resizes itself with a small inline script so it always spans the full width of the header, on any screen size or aspect ratio.
- Each project page embeds the live site in a browser-style window via `<iframe>`. If a site's host sends restrictive frame headers, the embed may not render — the "open directly ↗" link underneath is the fallback.

## Deploy on GitHub Pages

1. Push this folder's contents to the root of a repo (e.g. `if-else-repeat/oldmill`).
2. Repo → Settings → Pages → Source: `Deploy from a branch`, branch `main`, folder `/ (root)`.
3. Repo → Settings → Pages → Custom domain: `oldmill.in` (the `CNAME` file already sets this, GitHub will just confirm it).
4. At your DNS provider, point `oldmill.in` to GitHub Pages:
   - `A` records for the apex domain → GitHub's four Pages IPs (`185.199.108.153`, `.109.153`, `.110.153`, `.111.153`)
   - or an `ALIAS`/`ANAME` record if your DNS supports it.
5. Wait for DNS to propagate, then enable **Enforce HTTPS** in the Pages settings once the certificate is issued.

## Adding a new project card later

Duplicate the `.project-card` block in `index.html`, then duplicate the `rabbithole/` or `archive/` folder as a template for the new doc page — swap the logo, copy, and live link.
