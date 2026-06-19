# X Advanced Search Builder

A single-file tool that compiles X (Twitter) advanced-search queries from a form, then opens them live on X. No build step, no dependencies, no data leaves the page.

Designed as a "casefile instrument": warm-paper palette, a single signal accent, IBM Plex Mono / Space Grotesk type, and a live compiled-query readout.

## Features

- **Words** - all-of, exact phrase, any-of (`OR` grouping), exclusions, hashtags, language.
- **Accounts** - `from:`, `to:`, and `@mention`.
- **Time window** - `since` / `until` by date, with an optional time field that emits the `YYYY-MM-DD_HH:MM:SS_UTC` form.
- **Engagement thresholds** - `min_replies:`, `min_faves:`, `min_retweets:`.
- **Filters** - media, images, videos, native video, verified, blue verified, replies, reposts, quotes, news (each as a toggle, with exclude variants).
- **Geo** - `near:` / `within:`, or a `geocode:` form when given `lat,long`.
- **Quick presets** - one-tap starting points grouped by intent: engagement (viral on topic, viral verified, viral video, heated conversation, widely reposted), content type (original-only, verified originals, media/images/videos/native clips, verified, reply threads, quotes, news, links), language (English image posts, Persian/Arabic/Russian/Hebrew media), and relative time (last 7 days, last 24 hours - computed in UTC at click time). Presets merge into the current form rather than resetting it.
- **Live readout** - syntax-highlighted query plus the full `x.com/search` URL, with copy-query, copy-URL, open, and reset actions.
- **Mobile** - the query panel becomes a bottom-sheet drawer so the result stays reachable while filling the form; touch-sized controls, no iOS focus-zoom.

## Usage

Open `index.html` in any modern browser. Fill fields; the query and URL build themselves. Use **Open on X** to run it live.

Everything runs client-side. There is no server and no telemetry.

## Deploy on Vercel

This is a static site with no build.

**From the dashboard:** import the GitHub repo at <https://vercel.com/new>. Framework preset = **Other**, leave build command and output directory empty. Deploy.

**From the CLI:**

```bash
npm i -g vercel
vercel        # preview
vercel --prod # production
```

The entry point is `index.html`, so Vercel serves the tool at the root URL with no build and no rewrite. `vercel.json` just sets `cleanUrls` and a couple of security headers.

## License

MIT
