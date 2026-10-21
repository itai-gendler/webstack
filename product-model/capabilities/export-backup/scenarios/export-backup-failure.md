---
kind: edge
routes:
  android: Android
steps:
- text: Choose an export destination.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Attempt to write bookmark content.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
    - Title
    - Category
    - Saved at
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Report the write error.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
---

# Report a failed export

## Trigger

The chosen file cannot be written.

## Outcome

The app says the export failed; the bookmarks are untouched.
