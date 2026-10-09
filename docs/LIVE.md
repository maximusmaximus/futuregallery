# Admin live view

Locked from product direction on 2026-10-08.

Admin can pair a desktop screen to a show and watch live visitor interactions.

## Where it lives

- Desktop only. The admin signs in on a desktop browser.
- On that show’s details page, the menu includes Live view.
- Mobile visitor flow stays camera-first. Visitors never see this screen.

## Pairing

- From show details, admin chooses Pair screen.
- The desktop shows a short pair code. The same admin account confirms it, or a second desktop opens the code and links to this show.
- A paired screen stays on Live view for that show until the admin unpairs it or the session ends.
- Pairing is per show. One desktop can follow one show at a time.

## What the live feed shows

Detailed events, newest first, for the signed-in visitors on that show:

- Entered the exhibit
- Completed or skipped the first-time walkthrough
- Looked at a work (recognition held long enough to count as a look)
- Opened the overlay
- Checked or unchecked the grey-to-green investigate box
- Opened review
- Looked at the magnified piece, dimensions, cost, or availability
- Commented
- Marked purchase interest or started a purchase
- Shared the show
- Failed sign-in, bad code, or camera error, including why

Each row shows time, visitor name if they are signed in, the work title when there is one, and the action. Anonymous presence before sign-in shows as Guest, with no camera frame.

## Rules

- Admin of that show only.
- No raw camera frames.
- Names and emails already stored for the show stay in that show’s Google Drive spreadsheet. Live view reads the same identity, it does not invent a second list.
- The feed updates while the desktop page is open.
