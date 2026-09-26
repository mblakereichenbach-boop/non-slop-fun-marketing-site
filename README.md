# Non-Slop Fun — marketing site

Landing page for the Non-Slop Fun newsletter, served at **join.nonslopfun.com**.
The newsletter itself (posts, archive, reading series) stays on beehiiv at nonslopfun.com.

Plain static HTML/CSS with no build step. Signups go through the beehiiv embed form
(`912edc71-d96d-4d8b-a3df-262652eae834`).

## Files

- `index.html`: the page
- `styles.css`: all styles (desktop, tablet ≤1080px, phone ≤700px)
- `assets/`: collages, author photo, favicon, and share image (1200×630)
- `netlify.toml`: publish settings, caching, and short-link redirects

## Deploy on Netlify

1. Push this folder to the GitHub repo.
2. Netlify → **Add new site → Import an existing project → GitHub** → pick `non-slop-fun-marketing-site`.
   Leave the build command empty. The publish directory is `.` (already set in `netlify.toml`).
3. Site settings → **Domain management → Add a domain** → `join.nonslopfun.com`.
4. At your DNS provider, add a CNAME record: `join` → `<your-site-name>.netlify.app`.
5. Netlify issues the HTTPS certificate automatically once DNS resolves.

## Updating the "Latest issue"

Swap the image in `assets/`, then edit the title, excerpt and link in the first
`<article class="sample">` block of `index.html`.
