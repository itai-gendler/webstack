---
kind: edge
routes:
  android: Android
steps:
- text: Choose a backup document.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Report that the document could not be opened or parsed.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
---

# Report an unreadable backup

## Trigger

The chosen backup cannot be opened or read as a WebStack backup.

## Outcome

The app says the restore failed, and nothing on the device changes.
