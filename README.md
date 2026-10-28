# vamsi-calendar

My interview availability, as a single page anyone can open.

**https://vamsi05220323.github.io/vamsi-calendar**

Monday to Friday, 8am to 7pm Central, in one-hour slots. A recruiter sees the whole
week at once instead of clicking through one day at a time, and the times are shown
in their own time zone rather than mine.

## How it works

One static file, no build step, no dependencies. `index.html` holds both the data and
the page that renders it.

- **Time zones.** Hours are stored in Central. The dropdown relabels them for Eastern,
  Mountain or Pacific, and the page preselects the visitor's own zone by comparing
  their UTC offset against Central's — not by matching city names, so it stays correct
  through daylight saving changes and in places like Arizona that don't observe them.
- **Weeks.** Opens on the current week; the arrows reach four weeks ahead.
- **Read-only.** The cells are plain elements, not buttons. Nothing here to click.

## Changing my availability

Edit the `BUSY` block at the top of the `<script>` in `index.html`. Nothing else in
the file needs to change.

```js
var BUSY = {
  "2026-10-26": {            // the Monday of the week
    "2026-10-27": [9, 14]    // block 9–10am and 2–3pm Central on that Tuesday
  }
};
```

Hours are 24-hour Central time, and each number is the hour the slot *starts*. A day
that isn't listed is open all day, and so is a week that isn't listed. Commit and push;
GitHub Pages redeploys within a minute.
