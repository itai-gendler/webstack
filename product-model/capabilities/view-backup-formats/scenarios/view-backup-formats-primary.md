---
kind: primary
routes:
  android: Android
steps:
- text: Inspect the available backup formats and transfer explanation.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Show the bookmark count and explain application backups and browser bookmark files.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
  actor: user
  contexts:
    android:
      place: android::backup-restore
---

# See the backup formats

## Trigger

The User opens Backup & Restore and asks about the formats.

## Outcome

The number of saved links is shown with what .webstack, .html and .json files are for.
