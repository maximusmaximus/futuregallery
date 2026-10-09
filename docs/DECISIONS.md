# FutureGallery locked decisions

From the polish questionnaire on 2026-10-08. Free text overrides a plain yes or no. The add control stays at the bottom right, slightly below the artwork.

## Entry

- The visitor enters the exhibit and lands in an active camera view, with short instructions.
- First visit: a simple walkthrough while the camera is already up.
- Entry code is a QR, not a typed code.
- A bad or expired code tells them to contact the admin. It does not dump them into a blank camera.
- Camera permission is asked only after the code is accepted.
- If camera permission is denied, do not fall back to a catalog. They need the camera for this path.
- Public shows can be browsed without an account.

## Sign-in, purchase, records

- Saving an investigation list, or making a purchase, requires Google or X sign-in.
- Every email and name is stored in a Google Drive spreadsheet for that show.
- Sign-in is a sheet over the camera, with Google and X named on the buttons.
- On failure, retry once. Then ask them to notify the admin.
- The admin account sees errors and failed attempts, including why.

## Select and review

- The only select control is a checkbox at the bottom right, slightly below the artwork. Grey until selected, then green.
- After one or more are selected, they can open review.
- Haptic tap on select, where the phone supports it.
- The tray survives phone lock.
- Cap at 24. Then ask them to review before adding more.
- Review is a grid in the order they added the works.
- The first item is magnified and shows the art, dimensions, cost, availability, and comments.
- Comments require sign-in.
- Audio plays only on tap. Never autoplay.
- Closing review returns to the camera with the tray intact.

## Recognition

- A low-confidence match never opens the overlay by itself.
- Do not show a Not sure chip, a Wrong piece control, or a No work recognized empty state.
- Dark or blurry frames coach: move closer or add light. Do not false-match.
- Recognition pauses while an overlay is open.
- Overlay type is at least 18px and readable in gallery light.

## Public display and admin

- The public UI follows gallery display principles, not a single phone column and not the camera checkbox on catalog cards.
- A banner is required before publish.
- Cover photo is a cropped image of the work. Admin must pick one enrollment image and may crop it before publishing.
- Admin can unpublish without deleting the exhibit.
- Admin can undo the last enroll scan.
- Deleting an object requires confirmation. Old trays show Removed.
- Overlay text can be edited without a new scan.
- Empty overlay content is hidden, not shown as a blank card.
- Admin can set a price and mark a work for sale or not for sale.

## Share, privacy, data

- No visitor comments are public to other visitors until they are signed in to read them.
- Private notes are not a separate visitor feature in this pass. Comments are the note path, and they require sign-in.
- Share links include the show content that is visible, plus comments. Open Graph image is the main piece.
- Web viewers who want to read comments must sign in. Their email and name go to that show’s spreadsheet.
- Analytics store only the minimum needed, on the logged-in user’s row in the spreadsheet. No raw camera frames.
- Ask before using a scan to improve matching.
- Account delete removes trays, notes, and OAuth linkage within 30 days.
- Admin export is a zip of exhibit text and public images, not enrollment frames.

## Runtime

- Already opened public exhibit text works offline.
- Recognition requires a network in v1.
- Idle session ends after 8 hours. A signed-in tray is saved.
- One exhibit is one room in v1.
- English, plus accessibility support where possible. Not English-only with no a11y.
- Do not limit support to Safari and Chrome only.
- No kiosk mode.
- This is a web application only for now. No app stores.

## Explicitly not in this pass

- Typed entry codes.
- Catalog fallback when the camera is denied.
- Autoplay audio.
- Auto-opened weak matches.
- Wrong-piece reject control.
- Kiosk mode.
- Native store apps.
- Multi-room maps.
