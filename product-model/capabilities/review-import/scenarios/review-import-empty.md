---
kind: edge
routes:
  android: Android
steps:
- text: Choose a browser export file.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Report that no usable links were found.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
---

# Report a file with no importable links

## Trigger

The chosen browser file holds no HTTP or HTTPS links.

## Outcome

The app says no bookmarks were found, and no review opens.
