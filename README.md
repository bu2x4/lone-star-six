# Lone Star Six Interactive Playbook

Static, mobile-first player playbook for the Texas 6s Stampede 7th and 8th grade team.

## How it deploys

The site is a Cloudflare Worker with static assets (project `lone-star-six`), connected to this repo through Workers Builds.

- Everything the public sees lives in `public/`. Files outside it (this README, `wrangler.jsonc`) are never published.
- Every commit to `main` triggers a Cloudflare build that runs `npx wrangler deploy`. No build command is needed.
- The live site is `https://sixlax.app`.
- `public/_headers` sets security headers and keeps `sw.js` uncached.
- When changing `index.html`, bump the cache name in `public/sw.js` (for example `v4` to `v5`) so phones pick up the new version.

## Field Lab What If mode

Open the Field Lab, choose a situation, and press the large **Open What If Lab** button above the field. Players can drag any Lone Star or opponent marker to a new location. On release, the board explains the resulting spacing, matchup, substitution, field-rule, or defensive-shape consequence. Press reset to restore the designed play.

The goalie clear assumes a settled five-player zone. Wide outlets are the first reads. A middle outlet is used only when the receiver is already beyond midfield.

The substitution zone is marked on the right sideline at midfield. The Safe Change scenario routes both the exiting player and replacement through that sideline zone.

## Local preview

Run a static server from the `public` folder, for example:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Files

- `public/index.html`: complete application, styles, diagrams, animations, quiz, and completion card.
- `public/sw.js`: optional offline cache after the first visit.
