# vamsi-calendar

A short, permanent link to my interview availability calendar.

**https://vamsi05220323.github.io/vamsi-calendar**

## Why this exists

The calendar itself lives at a long, auto-generated URL that isn't practical to put
on a resume or type out in an email. This repo serves a one-page redirect so I can
hand out a readable link instead.

The more useful reason is indirection: if the calendar ever moves, I update
`index.html` here rather than chasing down every application and resume that
already went out. The public link stays the same.

## How it works

`index.html` redirects three ways, so it works regardless of how strict the
visitor's browser is:

- `<meta http-equiv="refresh">` — fires without JavaScript
- `location.replace()` — faster, and keeps the Back button sane
- a visible link — the fallback if both are blocked

The page is styled so that the brief moment before the redirect doesn't look broken.

## Updating the destination

Change the URL in all four places in `index.html` (the `canonical` link, the
`refresh` meta, the anchor `href`, and the `location.replace` call), then commit
and push. GitHub Pages redeploys on its own within a minute or so.
