# Chalk Line — Pool League Scheduler

Home-and-away scheduling for pool leagues where bars share tables and teams share bars.

## What's here

- `index.html` — the full app. Self-contained (React/Babel loaded from CDN, no build step). This is what gets deployed via GitHub Pages.
- `chalk-line-scheduler.jsx` — the source component, kept for reference/future edits.

## Turning access on/off

The deployed page checks a small JSON config hosted in a GitHub Gist before letting anyone in:

```json
{ "open": true, "code": "chalklive" }
```

- Set `"open": false` to take the tool offline for everyone (shows a "not open right now" screen).
- Change `"code"` any time to change the access code testers need to type in.
- Edits to the gist take effect the next time someone loads the page — no redeploy needed.

**Edit the live switch here:** https://gist.github.com/tnrmktng/aeb9d09be2f1c3cd30a36b2cebb90518

Current access code: `chalklive`

Note: `chalk-line-access.json` in this repo is just the template used to seed the gist — editing it does nothing to the live site. Only edits made directly on the gist page above take effect.

## Deploying changes

Any edit to `index.html`, committed and pushed to `main`, goes live automatically via GitHub Pages within a minute or two.
