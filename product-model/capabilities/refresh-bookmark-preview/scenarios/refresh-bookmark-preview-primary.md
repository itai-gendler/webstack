---
kind: primary
routes:
  android: Android
steps:
- text: Request a new preview for the bookmark.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Preview
  actor: user
  contexts:
    android:
      place: android::home
- text: Discard the bookmark’s previous preview and fetch a replacement.
  kind: product
  entities:
  - entity: bookmark
    effect: changes
    facts:
    - Preview
  actor: user
  contexts:
    android:
      place: android::home
---

# Refresh a bookmark's preview

## Trigger

With Fetch Web Previews on, the User chooses to refresh a bookmark's preview.

## Outcome

The old preview is discarded and a fresh one is fetched and kept on the device.
