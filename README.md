# Non-Slop Fun — marketing site

Landing page for the Non-Slop Fun newsletter, served at **join.nonslopfun.com**.
The newsletter itself (posts, archive, reading series) lives on Substack at nonslopfun.com.

Plain static HTML/CSS with no build step. Signups go through the Substack embed
(`https://nonslopfun.substack.com/embed`, an iframe).

## Files

- `index.html`: the page
- `styles.css`: all styles (desktop, tablet ≤1080px, phone ≤700px)
- `assets/`: collages, author photo, favicon, and share image (1200×630)
- `netlify.toml`: publish settings, caching, and short-link redirects (the `/reading` redirect still needs a new target; see below)

## Deploy on Netlify

1. Push this folder to the GitHub repo.
2. Netlify → **Add new site → Import an existing project → GitHub** → pick `non-slop-fun-marketing-site`.
   Leave the build command empty. The publish directory is `.` (already set in `netlify.toml`).
3. Site settings → **Domain management → Add a domain** → `join.nonslopfun.com`.
4. At your DNS provider, add a CNAME record: `join` → `<your-site-name>.netlify.app`.
5. Netlify issues the HTTPS certificate automatically once DNS resolves.

## Changing the "Featured issue"

Optional, whenever you want to feature a different issue: swap the image in `assets/`, then edit the title, excerpt and link in the first
`<article class="sample">` block of `index.html`.

## Substack migration notes

- The signup form is Substack's iframe embed on the home page (twice) and the About page.
  Its styling is set by Substack; only the iframe's outer border and size are adjustable here.
- `/reading` in `netlify.toml` and the "Get the series free" / "Reading Challenge" links still
  point to the old beehiiv page `nonslopfun.com/rebuild-your-reading-habit`. Repoint them once
  the reading series has a new home.
- Featured-issue links use `nonslopfun.com/p/<slug>`; confirm the slugs match after the import.
