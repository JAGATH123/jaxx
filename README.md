# JAXX

A tiny personal AI landing page and chat interface — built for one person.

Static site. No build step, no dependencies, no framework.

## Structure

```
index.html     the page and the chat interface
styles.css     all styling
main.js        woven texture, nav, and the chat
assets/        sphere artwork (webp + png fallback)
vercel.json    cleanUrls + long-lived asset caching
```

## Running locally

Any static server works:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploying

Connected to Vercel. Pushing to `main` deploys.

`vercel.json` sets `cleanUrls` and caches `/assets/*` immutably for a year.
`styles.css` and `main.js` are deliberately left on default caching so
changes go live immediately.

## Notes

- The chat is a scripted demo — canned replies on a realistic delay. There is
  no API, no key, and no network call. All of its copy lives in one `SCRIPT`
  object at the top of the chat section in `main.js`.
- The thread persists to `localStorage`.
- Images ship as WebP with PNG fallbacks via `<picture>`.
- Fully usable without JavaScript: the page reads, scrolls and navigates.
- Honours `prefers-reduced-motion`.
