# FutureGallery: 50 open questions

Answer inline or in a reply. Implementation follows these answers. Defaults in parentheses are proposals, not decisions.

## Entry, registration, auth

1. What does the entry code represent: one code per exhibit, per room, or per artwork?
2. What does scanning it unlock: a session, exhibit access, an analytics id, or all three?
3. Must every visitor complete Google or X sign-in before the camera opens, or is the code enough for a guest session?
4. Should public shows allow an anonymous guest scan, with optional upgrade to an account to save selections?
5. Google sign-in: Supabase Auth, Firebase Auth, or Auth.js / custom OIDC? Any Workspace domain restriction?
6. X sign-in: OAuth 2.0 with PKCE, and do we store only user id + handle, or also a refresh token?
7. Is a visitor account global across exhibits, or scoped to one show?
8. Should we collect a display name and avatar from the provider, or keep identity minimal?
9. Session length on the gallery floor: hours, until tab close, or until the exhibit end time?
10. What happens if OAuth fails on poor gallery wifi: block entry, or allow a limited offline guest pass?

## Roles and admin governance

11. Does the first Google or X user automatically become the sole admin, or is admin granted only by invite code / allowlist?
12. Can one exhibit have multiple admins, and can an admin promote or revoke others?
13. Can one admin own multiple exhibits, and is the product multi-tenant from day one?
14. Which admin knobs must exist at launch: match confidence, minimum images, overlay theme, language, analytics on/off?
15. Do we need account deletion and export of scans, embeddings, and OAuth linkage in v1?
16. Should admin actions (enroll, publish, edit content) be audit-logged?

## Exhibits, banner, public and private

17. Is the banner a hero image plus title plus short text, and is the title the URL slug (for example `/show/neon-equinox`)?
18. Can the slug be edited after publish, and what happens to the old URL?
19. Slug uniqueness: global, or per admin?
20. Is private enforced by an allowlist, by an unguessable link, or both?
21. Who generates the entry code, and is it permanent or rotatable?
22. Does a private show hide metadata even if someone photographs a piece, or is privacy only the entry link?
23. Can an exhibit be scheduled (open and close times) or is publish/unpublish manual only?
24. Public catalog page: grid, editorial scroll, or both, and is the camera the primary path or the catalog?

## Object definition and vision

25. Is enrollment image-based tracking of known artwork photos, or open-world instance segmentation (tap any physical object and enroll it)?
26. Preferred vision stack: WebXR image tracking, MindAR / AR.js, MediaPipe, TensorFlow.js embeddings, server-side model, or hybrid? Must it work on iOS Safari and Android Chrome?
27. How does the admin isolate the object from the background: tap-to-segment, draw a box, or automatic foreground mask?
28. Completeness threshold: minimum image count, minimum distinct angles, embedding diversity score, admin override, or a combination?
29. What numeric defaults (proposal: 8 images, 4 angles, diversity score, publish blocked until met)?
30. Should the UI coach the admin ("need a side angle", "too similar to previous shot") or only show a count?
31. Do re-scans update the object in place, or version the definition so old embeddings remain?
32. When recognition confidence is below threshold, do we show "need a better angle" coaching, fall back to catalog search, or both?
33. When several enrolled objects are in frame, how do we disambiguate: closest, largest, highest confidence, or a list?
34. Are overlays anchored to the object plane (6DoF) or a floating card near the detection?

## Data, storage, matching

35. Database: Supabase (Postgres + pgvector + storage + auth), Firebase, self-hosted Postgres, or other?
36. Matching: image embeddings (CLIP-class) in a vector index, classic features (ORB), WebXR markers, or hybrid?
37. Where do reference images live, and do we keep originals plus crops and masks?
38. Do we store camera pose or approximate room coordinates per scan, or only visual embeddings?
39. Is there a named room or zone map the admin walks, or only a flat camera session per exhibit?
40. Upload limits and client-side compression before storage? Retention: keep every scan, or prune weak ones after the object is defined?
41. Content types required at launch: text, audio, video, 3D model, external link, artist bio, price. Which are in v1?
42. Content language: single locale, or per-overlay translations?

## Visitor camera UX and multi-select

43. Multi-select control: checkbox on each overlay, a thumbnail tray, or both?
44. Is a selection a session tray, a saved favorites list on the account, or both?
45. Can a visitor add private notes to a selection?
46. Can a multi-selection be shared as a link, or is review device-local only?
47. After selecting pieces, what is the review screen for: compare, read, listen, save, or inquire?
48. Analytics: anonymous scan counts only, or tied to the signed-in identity? Opt-in or on by default for public shows?

## Product, legal, delivery

49. License for this public repo: MIT, Apache-2.0, or source-available until a later decision?
50. Deploy target for the first running build: Vercel, Cloudflare, self-hosted, or repo-only until the questions above are answered? Should the starter include a schema migration and a mock exhibit, or docs only until then?
