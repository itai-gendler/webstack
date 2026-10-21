---
kind: validation
routes:
  android: Android
steps:
- text: Choose a document for import.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Report the unsupported format.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
---

# Refuse a file that is neither a backup nor a bookmark file

## Trigger

The chosen file has another extension, or neither its name nor its content shows it is a backup or a browser bookmark file.

## Outcome

The app asks for a .webstack, .json, .html or .htm file, and nothing is imported.
