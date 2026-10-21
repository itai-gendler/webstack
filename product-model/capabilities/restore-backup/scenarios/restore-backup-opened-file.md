---
kind: alternate
routes:
  android: Android
steps:
- text: Open a WebStack backup with the Android app.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::home
- text: Parse and merge the file with existing bookmark and tag content.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
  - entity: tag
    effect: reads
    facts:
    - Name
  actor: user
  contexts:
    android:
      place: android::home
- text: Add a missing tag and a new bookmark from the backup.
  kind: product
  entities:
  - entity: tag
    effect: creates
    facts:
    - Name
    - Position
    to: Active
  - entity: bookmark
    effect: creates
    facts:
    - URL
    - Title
    - Domain
    - Category
    - Saved at
    - Source folders
    - Preview
    - Selected
  actor: user
  contexts:
    android:
      place: android::home
- text: Report the restoration result.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::home
---

# Restore an externally opened backup

## Trigger

The User opens a .webstack file with WebStack from a file manager or another app.

## Outcome

The backup is merged the same way as from Backup & Restore, and the app says what was restored.
