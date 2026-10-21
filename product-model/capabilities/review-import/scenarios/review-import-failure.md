---
kind: edge
routes:
  android: Android
steps:
- text: Choose a browser export document.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Report the file-open or parse error.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
---

# Report a preparation failure

## Trigger

The chosen browser file cannot be opened or read.

## Outcome

The app says the bookmarks could not be read, and no review opens.
