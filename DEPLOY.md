# astroformcorp.com — deploy notes

Static landing page for Astroform. Single self-contained `index.html` (images embedded),
plus `CNAME` for the GitHub Pages custom domain. Contact form posts to Formspree
(`https://formspree.io/f/maenwdge`); no backend needed.

## Hosting: GitHub Pages

Repo: `trevor857886/astroformcorp.com`, public, branch `main`, folder `/ (root)`.
Custom domain: `astroformcorp.com` (set by the `CNAME` file). Enforce HTTPS once the
certificate is issued.

## DNS (GoDaddy) — must be done by hand in the GoDaddy dashboard

Remove any existing `@` A record (GoDaddy "parked" placeholder), then add:

| Type  | Name | Value                     |
|-------|------|---------------------------|
| A     | @    | 185.199.108.153           |
| A     | @    | 185.199.109.153           |
| A     | @    | 185.199.110.153           |
| A     | @    | 185.199.111.153           |
| CNAME | www  | trevor857886.github.io    |

Propagation is usually 10–60 minutes. Then in the repo's Settings → Pages, tick
"Enforce HTTPS" (greyed out until the cert is issued; wait and retry).

## Updating the site later

Replace `index.html`, commit, push. Pages redeploys in about a minute.
