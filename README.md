# FutureGallery

Unattended gallery, as a web app. A visitor scans a QR, the camera opens, and recognized works show extra information. They can check pieces to investigate and review them. An admin enrolls the works, publishes the show, and can watch what people do from a paired desktop.

This is a web application only. No app store build in this pass.

Public repository: https://github.com/maximusmaximus/futuregallery

Decisions: [docs/DECISIONS.md](docs/DECISIONS.md). Live desktop: [docs/LIVE.md](docs/LIVE.md).

## What a visitor should expect

- You scan the show QR and land in a live camera, with short instructions. The first visit adds a simple walkthrough while the camera is already up.
- The camera asks for permission only after the code is accepted. If you deny it, this path stops. There is no catalog fallback.
- A bad or expired code tells you to contact the admin. It does not open a blank camera.
- Point the phone at a work. A clear match can show an overlay. A weak match does not open by itself. Dark or blurry frames ask you to move closer or add light.
- Under each recognized work, bottom right and slightly below the piece, a checkbox goes from grey to green. That adds it to your items to investigate. Tap again to remove it. A short haptic plays when the phone supports it.
- After one or more checks, you can open review. Review is a grid in the order you added them. The first item is magnified, with the art, dimensions, cost, availability, and comments.
- Comments need Google or X sign-in. Sign-in is a sheet over the camera. The buttons say Google and X.
- Audio plays only if you tap it. It never starts on its own.
- You can browse a public show without an account. Saving the list, commenting, reading comments, or buying requires sign-in. Your name and email go to that show’s Google Drive spreadsheet.
- The list survives locking the phone. It holds up to 24 pieces, then asks you to review before adding more. Closing review returns you to the camera with the list intact.
- If sign-in fails, it retries once, then asks you to notify the admin.
- Share links include the visible show and its comments. The preview image is the main piece.
- Text you already opened can be read offline. Recognizing a work needs a network.

## What an admin should expect

- You sign in with Google or X and create the show. You set the banner, which is required to publish, and choose public or private. The banner title is the slug.
- You walk the room, isolate a work from the background, and define it with several images and angles. The app tells you when it still needs more. You can undo the last scan. You can edit overlay text without scanning again.
- Before publish, you pick one enrollment image as the cover and you can crop it. Enrollment frames are not the public catalog.
- You can set a price and mark a work for sale or not for sale. You can unpublish without deleting the show. Deleting a work asks you to confirm. Old visitor lists then show Removed.
- On a desktop, open that show’s details. The menu includes Live view. Pair a screen to this show. The paired desktop stays on the live feed until you unpair it.
- Live view is the detail of what people did: entered, looked at a work, checked it, opened review, read cost or availability, commented, showed purchase interest, shared, or failed, including why. Signed-in people appear by name. Others are Guest. No camera frames. Only the admin of that show sees it.
- Names, emails, and the minimum analytics sit on that show’s Google Drive spreadsheet, on the signed-in user’s row. Failed attempts and the reason are visible on the admin account.
- Export is a zip of exhibit text and public images, not the enrollment frames. Account deletion removes trays, notes, and the sign-in link within 30 days.

## What this pass is not

- Not a native iOS or Android app.
- Not a kiosk mode, and not a multi-room map. One exhibit is one room.
- Not a public comment thread for people who are not signed in.
- Not a place that stores raw camera frames.

## In this repo

- [docs/DECISIONS.md](docs/DECISIONS.md) — locked answers
- [docs/LIVE.md](docs/LIVE.md) — paired desktop live view
- [docs/OVERLAY.md](docs/OVERLAY.md) — checkbox under the artwork
- [prototype/index.html](prototype/index.html) — visitor select and review tray
- [prototype/admin-live.html](prototype/admin-live.html) — desktop Live view

License is not set. Do not treat this repository as reusable until that is decided.
