---
kind: edge
routes:
  android: Android
steps:
- text: Open the bookmark.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Report that no browser could be opened.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
---

# Report a browser hand-off failure

## Trigger

The Android browser hand-off fails.

## Outcome

The app reports that it could not open the browser; the saved item remains.
