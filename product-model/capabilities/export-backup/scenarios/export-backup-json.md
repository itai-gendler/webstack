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
- text: Write bookmark content and active tag names in JSON backup format.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
    - Title
    - Category
    - Saved at
  - entity: tag
    effect: reads
    facts:
    - Name
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

# Export a JSON backup

## Trigger

In Backup & Restore, the User chooses Export Backup as .json and picks where to save the file.

## Outcome

The file holds the same content as a .webstack backup, in plain JSON.

## Edge cases

- Cancelling the document picker leaves the stack unchanged.
