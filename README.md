# FOXON progress

Proposed live page: <https://four2d.github.io/foxon-progress/>

This repository is meant to be the public, page-only copy of the FOXON progress page. It shows where Invoice, CIS, Miles, Gas and Books are, what is left to do, and a feature checklist. Percentages are worked out from `features.json`.

This staging copy has not been published. Do not create the GitHub repository, enable Pages, or add a remote until Pete says so in chat.

## How to update

Once this is a public repository, edit the files and push to `main`. GitHub Pages would publish from `main`.

1. `git pull --ff-only` first. Never force-push.
2. Edit `features.json` for checklist ticks and percentages. Edit `index.html` for the facts on the page (date, callouts, what’s next, blockers, timelines). Edit `NEXT.md` when the public work queue changes.
3. Do not put passwords, keys, tokens, private email addresses, phone numbers, addresses, bank or finance figures, case numbers, account IDs, or internal machine paths in this repository.
4. Make sure `features.json` is still valid JSON (`python3 -m json.tool features.json`).
5. Commit and `git push` to `main` (fast-forward only). Do not force-push.

Update after every significant change. If nothing has changed, do not update the files.

## How to tick an item

The checklist and every percentage on the page come from **`features.json`**. Do not type percentages into the page.

1. Find the item by its `id` in `features.json`, for example `"invoice-submit"`.
2. Set that platform’s `state` to one of these:
   - `done`: finished, and checked on a real phone or console where that applies
   - `part`: built or drafted, but not checked or not finished
   - `todo`: not done
   - `na`: does not apply
3. Change the `note` so it says what is true now. Keep it short and factual. Never put a password, key, token or private detail in it.
4. Change `"updated"` to today’s date.
5. Make sure the file is still valid JSON, then commit and push.

To add an item, copy one that already exists and give it a new `id`. If a platform does not apply, leave that key out.

If someone clicks a box on the page, the tick is stored only in that browser’s localStorage and is labelled “Local tick, not yet saved”. It does not change the file or the percentages. To make it real, edit `features.json`.

## What else to edit in `index.html`

Edit only the facts.

1. The date line at the top (`.asof`) and in the footer.
2. The top `.call` and the two fixed stats (Invoice Android review, public releases). The Invoice and CIS percentages come from `features.json`.
3. The `apps` array in the script: tracks, rails, timeline points and the call line. A timeline point is `now` when it is on a phone or in current use, `past` when it is older and reached a device, and `wait` when it is only on a store track or staged, and not yet confirmed on the phone.
4. `stageRows`, which feeds the four-step chart.
5. The `#gap` callout and the “Written, not on the phone” list.
6. What’s next (`#next`) and Blockers (`#blockers`).

Do not invent a public release or a store state. Re-open App Store Connect or Play Console before you quote a version.

## Brand

Leave the layout, colours and type alone.

- Colours: black `#0b0b0b`, yellow `#f2c500`, ink `#f4f1e8`, muted `#a39e92`, card `#141414`, danger `#ff4d3a`.
- Headings use Oswald from Google Fonts. Body type is Avenir Next, then system sans-serif.
- The logo is `foxon-logo-horizontal-dark.svg`. Do not redraw it. Do not retype FOXON or SOFTWARE in the header.
