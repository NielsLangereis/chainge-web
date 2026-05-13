# chainge / deploy bundle

Production-ready static site for `chainge.global`. Drop this whole folder into Netlify, you're live.

## What's in here

- `index.html` — the marketing site
- `favicon.svg` — the chain mark, in brand colors
- `og-image.svg` — social share card, 1200×630
- `netlify.toml` — basic config (security headers, caching)
- `README.md` — this file

That's it. No build step, no dependencies, no package.json. The fonts load from Google's CDN, everything else is inline.

## Deploy in three minutes

### Option A: drag-and-drop (fastest)

1. Go to <https://app.netlify.com/drop>
2. Drag this folder (`chainge-deploy`) onto the page
3. Netlify gives you a `something-something-12345.netlify.app` URL immediately
4. Test the page works. The email form will submit to Netlify Forms automatically.
5. In Netlify dashboard → Domain settings → add custom domain `chainge.global`
6. Update DNS at your domain registrar to point to Netlify (Netlify shows you exactly what records)

### Option B: connect a Git repo (better long-term)

1. Push this folder to a Git repo (GitHub, GitLab, Bitbucket)
2. In Netlify: New site from Git → connect repo → deploy
3. Every push to `main` auto-deploys
4. Same domain setup as Option A

## Email subscriptions

The "stay in the loop" form is wired to Netlify Forms (free for the first 100 submissions/month).

After first deploy:
1. Netlify dashboard → your site → Forms
2. You'll see `subscribe` as a form
3. Form submissions appear there with the submitter's email
4. Set up email notifications: Forms → Settings → Form notifications → add `mail@nielslangereis.com`

To export subscribers later, you can download a CSV from the Forms tab.

## Partner contact

The "talk to niels" button is a `mailto:` link pointing at `mail@nielslangereis.com`. No backend needed.

## OG / Twitter previews

The `og-image.svg` is referenced in the OG and Twitter meta tags. SVG is supported by most modern crawlers; LinkedIn, X, and Slack render it fine. If you want guaranteed compatibility with older crawlers, generate a PNG version at 1200×630 and update the meta tags to point at it.

You can test how the page looks when shared at:
- <https://www.opengraph.xyz/>
- <https://cards-dev.twitter.com/validator>

## Things to tune after first deploy

- **Real subscriber email destination.** Currently routes to `mail@nielslangereis.com`. Change in Netlify Forms settings if you want a separate inbox.
- **Robots / indexing.** Currently set to `index, follow`. Flip to `noindex` in `<head>` if you want stealth before launch.
- **Analytics.** Not included. Recommend Plausible (`<script defer data-domain="chainge.global" src="https://plausible.io/js/script.js"></script>`) — privacy-friendly, lightweight, no GDPR banner needed.
- **Custom 404 page.** Add `404.html` to this folder when you want one. Netlify picks it up automatically.

## Editing

The whole site is one file: `index.html`. CSS lives in the `<style>` block at the top, JS in the `<script>` block at the bottom. The design tokens (colors, fonts) are in the `:root` block of the CSS, near the top. Change them there and they propagate everywhere.

Source of truth for the design system is `chainge-tokens.css` in the parent folder. Keep both in sync if you make brand changes.

## When you change content

The chain narratives, profile personas, and section copy are all in `index.html`. The site is small enough that find-and-replace works. Search for:

- `chain-a`, `chain-b`, `chain-c` — the three hero chains
- `Anne`, `Pieter`, `Camila` — the three profile personas
- `qualitative quant` — appears once as the undermark
- `McKinsey` — appears once as the institutional positioning anchor

## Versioning

This is v0.2.1 of the page. Iterate the file in place, push to deploy. Netlify keeps a history of every deploy, so reverting is one click.
