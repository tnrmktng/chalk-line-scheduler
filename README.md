# Chalk Line — Pool League Scheduler

Home-and-away scheduling for pool leagues where bars share tables and teams share bars.

## What's here

- `index.html` — the full app. Self-contained (React/Babel loaded from CDN, no build step). This is what gets deployed via GitHub Pages.
- `chalk-line-scheduler.jsx` — the source component, kept for reference/future edits.

## Turning access on/off

**Default link** (no `?league=` in the URL — https://tnrmktng.github.io/chalk-line-scheduler/):
gated by one gist, same as a single-league setup.

- **Edit the live switch:** https://gist.github.com/tnrmktng/aeb9d09be2f1c3cd30a36b2cebb90518
- Current access code: `chalklive`
- Set `"open": false` to take the tool offline (shows a "not open right now" screen). Change `"code"` to rotate the code. Edits take effect next page load — no redeploy needed.

## Multiple leagues

Every league gets its own link, its own access code, and its own on/off switch, all pointing at the same deployed page — turning one league off doesn't touch any other.

**Directory gist** (maps league slug → that league's access gist): https://gist.github.com/tnrmktng/819b4978f9a682a1624d585e4ec82d7f

To onboard a new league (no code change, no redeploy):

1. Create a new public gist, e.g. `chalk-line-access-<league>.json`, containing `{ "open": true, "code": "yourcode" }`. Copy its Raw URL.
2. Add a line to the directory gist above: `"<slug>": "<that raw URL>"`.
3. Send that league this link: `https://tnrmktng.github.io/chalk-line-scheduler/?league=<slug>`.

Existing demo league for reference: `?league=demo`, code `demolive`, gist at https://gist.github.com/tnrmktng/b7513aa05c7641753dd81b22e915dd07

Each league's schedule data is also kept separate automatically (stored per-link in each visitor's own browser).

Note: the `chalk-line-*.json` files in this repo are just templates used to seed the gists — editing them here does nothing to the live site. Only edits made directly on the gist pages above take effect.

## Deploying changes

Any edit to `index.html`, committed and pushed to `main`, goes live automatically via GitHub Pages within a minute or two.
