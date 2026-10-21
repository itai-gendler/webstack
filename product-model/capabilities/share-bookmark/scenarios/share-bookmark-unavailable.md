---
kind: edge
routes:
  android: Android
steps:
- text: Share the bookmark.
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
- text: Report that the link could not be shared.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
---

# Report a sharing failure

## Trigger

Android sharing cannot be opened.

## Outcome

The app reports the sharing failure and keeps the saved item.
