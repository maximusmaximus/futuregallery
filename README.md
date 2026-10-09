# FutureGallery

Unattended gallery mobile web app. A visitor scans an entry code, signs in with Google or X, then points their camera at works in the room. Recognized objects get overlays with extra information. An admin enrolls each work with multiple scans until a completeness threshold is met, then attaches content and publishes the exhibit as public or private.

Public repository: https://github.com/maximusmaximus/futuregallery

This repo is a design home. Product decisions are open. See [docs/QUESTIONS.md](docs/QUESTIONS.md) (50 questions). Implementation starts after those answers.

## What is already specified

- Mobile web, not a native app.
- Entry by scanning a code, which registers the visitor to scan objects in the room.
- Camera view with overlays for additional information about a recognized object.
- Unattended gallery: no staff required on the floor.
- Sign-in with Google or X. An admin signs in first and sets parameters.
- Admin walks the room, isolates an object from the background, and defines it with several images and angles.
- A threshold tells the admin when the object is not yet clearly defined.
- A database stores reference images, embeddings, and content so later scans can recall the object for viewing or management.
- Visitors can check multiple works while using the camera and review the selection.
- Admin creates exhibits and updates a banner that is the main slug for the show.
- Admin chooses public or private.
- Public shows need a clear, creative presentation of each artwork.

## Working assumptions (not decisions)

These are placeholders so the repo has a shape. Every one is questioned in `docs/QUESTIONS.md`.

- PWA: Vite + React, installable, camera via `getUserMedia`.
- Recognition: hybrid. WebXR image tracking where the browser supports it, otherwise client embeddings (CLIP-class or MobileNet) matched against pgvector. Admin enrollment uses tap-to-mask plus extra angles.
- Data: Postgres + pgvector + object storage. Supabase is the default candidate because it covers auth, storage, and vectors.
- Auth: Google via the auth provider. X via OAuth 2.0 PKCE. First signed-in user can become admin only if we confirm that rule.
- Deploy: undecided. Repo only until answers land.

## Layout

```
docs/QUESTIONS.md      50 open questions
docs/ARCHITECTURE.md   proposed flows and components
docs/SCHEMA.md         draft tables
```

## License

Unspecified until question 49 is answered. Do not treat this repository as licensed for reuse yet.
