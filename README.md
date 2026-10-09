# Heartware corporate demo (Acme)

A copy of the birthday guest site, reworked for a corporate client. Everything here is fictional: Acme Inc., the 25 guests in `guest-roles.csv` and their access codes. The live birthday site and its repo are untouched.

Live: https://heidihyn.github.io/heartware-demo/. GitHub Pages serves the repo root from `main`; `node build.mjs` copies the pages there.

## What's here
- `site.src.html`: the guest page (schedule, content rating, roles, access-code lookup, venue, drinks, food, NDA, team vote, music, photos, feedback).
- `invite.src.html`: the invite email and the printed 5 × 3.5 in card, one per guest, each with that guest's access code. Print from a browser to get every card.
- `show.src.html`: the projector show (lobby to mingle, plus the party add-on and stand by) with sound. Use it in a browser tab, or in OBS as one Browser source per scene: `show.html#lobby`, `#keynote`, `#incident`, `#teams`, `#investigation`, `#ten`, `#huddle`, `#vote`, `#review`, `#awards`, `#mingle`, `#party`, `#standby`. Tick "Control audio via OBS".
- `show-media/`: the big sound cues from HeartwareMedia-kit (death, boot-up, investigation bed, chime, heartbeat). Smaller effects are generated in the page.
- `src/nda.html`: the corporate NDA. `nda.pdf` and `nda-share.png` are rendered from it.
- `config.json`: client name, contact, content rating (`G`, `PG`, `PG-13`), `danceFloor` add-on on or off, `fireWord` (`fire` or `deactivate`), calendar times, demo codes.
- `guest-roles.csv`: the roster (name, role, team, who a Witness knows, code). `guest-codes.md` is generated from it.

## Update
1. Edit the `.src.html` files, `config.json` or `guest-roles.csv`.
2. `node build.mjs` writes `index.html`, `invite.html`, `show.html` and a hostable copy in `standalone/`.
3. Commit and push. Pages redeploys in about a minute.
