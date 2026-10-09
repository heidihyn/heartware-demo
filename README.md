# Heartware corporate demo (Acme)

A copy of the birthday guest site, reworked for a corporate client. Everything here is fictional: Acme Inc., the 25 guests in `guest-roles.csv` and their access codes. The live birthday site and its repo are untouched.

Live: https://heidihyn.github.io/heartware-demo/ (show control: /control.html, wall: /show.html#wall). GitHub Pages republishes `standalone/` on every push to `main`.

## What's here
- `site.src.html`: the guest page (schedule, content rating, roles, access-code lookup, venue, drinks, food, NDA, team vote, music, photos, feedback).
- `invite.src.html`: the invite email and the printed 5 × 3.5 in card, one per guest, each with that guest's access code. Print from a browser to get every card.
- `show.src.html`: the projector show (lobby to mingle, plus the party add-on and stand by) with sound. Use it in a browser tab, or in OBS as one Browser source per scene: `show.html#lobby`, `#keynote`, `#incident`, `#teams`, `#investigation`, `#ten`, `#huddle`, `#vote`, `#review`, `#awards`, `#mingle`, `#party`, `#standby`. Tick "Control audio via OBS".
- `control.src.html`: the technician panel for running the show live. Open `control.html` in Chrome on the laptop, click "Open the wall window", drag that window to the projector screen and click it once (full screen, sound on). Scene buttons, timers, each team's vote, the verdict count, the three-step reveal and the awards all drive the wall live; the panel shows a muted preview. Votes and timers are saved in the browser, so a refresh loses nothing. For OBS, capture the wall window with Window Capture instead of using per-scene Browser sources.
- `show-media/`: the big sound cues from HeartwareMedia-kit (death, boot-up, investigation bed, chime, heartbeat). Smaller effects are generated in the page.
- `src/nda.html`: the corporate NDA. `nda.pdf` and `nda-share.png` are rendered from it.
- `config.json`: client name, contact, content rating (`G`, `PG`, `PG-13`), `danceFloor` add-on on or off, `fireWord` (`fire` or `deactivate`), calendar times, demo codes.
- `guest-roles.csv`: the roster (name, role, team, who a Witness knows, code). `guest-codes.md` is generated from it.

## Update
1. Edit the `.src.html` files, `config.json` or `guest-roles.csv`.
2. `node build.mjs` writes `index.html`, `invite.html`, `show.html` and a hostable copy in `standalone/`.
3. Commit and push. The Pages workflow publishes `standalone/`.
