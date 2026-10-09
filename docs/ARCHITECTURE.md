# Architecture (proposed, pending questions)

## Flows

### Admin enroll

1. Sign in with Google or X.
2. Create an exhibit. Set banner, slug, public or private.
3. Open the camera in the room.
4. Isolate an object from the background.
5. Capture several images and angles. The client shows a completeness meter.
6. Publish is blocked until the threshold is met, unless an override is allowed.
7. Attach overlay content. Save reference images, masks, and embeddings.

### Visitor

1. Scan the exhibit code.
2. Sign in, or enter as guest if that mode is enabled.
3. Camera opens on the exhibit.
4. Detections match stored embeddings or markers.
5. Overlay shows the attached content.
6. Checkbox adds the work to a review tray.
7. Review screen shows one or many selected works.

## Components

- Mobile PWA client: camera, enrollment UI, overlay UI, review tray, public catalog.
- Auth: Google and X.
- API: exhibits, objects, scans, content, selections.
- Postgres: relational records. Vector index: embeddings. Object storage: images, masks, media.
- Matching worker: embed on enroll and on visitor frame samples. Do not embed every video frame.

## Non-goals until answered

- Native iOS or Android apps.
- Full room SLAM or persistent spatial map.
- Payments or ticketing.
- Staff-moderated floor tools.

## Risks

- WebXR image tracking is uneven on iOS Safari. A hybrid with client embeddings is the fallback.
- Gallery lighting and glare will drop confidence. Coaching and catalog fallback are required.
- Embeddings of similar works (prints in a series) will collide. Admin needs a disambiguation review.
