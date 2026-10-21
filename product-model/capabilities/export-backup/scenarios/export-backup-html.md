---
kind: alternate
routes:
  android: Android
steps:
- text: Choose the export format and a destination document.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Write bookmark URLs, titles, and saved dates under category folders.
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
- text: Confirm that the export completed.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
---

# Export browser bookmarks

## Trigger

In Backup & Restore, the User chooses Export Backup as .html and picks where to save the file.

## Outcome

A standard browser bookmark file (Netscape format, UTF-8) is written, with one folder per tag and Uncategorized bookmarks at the top level.

## Edge cases

- Cancelling the document picker leaves the stack unchanged.
