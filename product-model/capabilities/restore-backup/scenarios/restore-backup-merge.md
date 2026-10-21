---
kind: primary
routes:
  android: Android
steps:
- text: Choose a WebStack or JSON backup document.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Parse the backup and compare its links and categories with saved content.
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
      place: android::backup-restore
- text: Create a missing active tag from the backup.
  kind: product
  entities:
  - entity: tag
    effect: creates
    facts:
    - Name
    - Position
    to: Active
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Create each new bookmark with the restored content and saved date.
  kind: product
  entities:
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
      place: android::backup-restore
- text: Report added links and new categories.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::backup-restore
---

# Merge a WebStack or JSON backup

## Trigger

The User chooses Import Backup in Backup & Restore and picks a .webstack or .json backup.

## Outcome

Links not already saved are added with their titles, tags and dates, and tags not yet present are added; bookmarks already saved are left as they are. The app says how many links and new tags were restored.

## Edge cases

- When all links already exist, report that they are already in the stack.
- Missing or blank titles use the address; missing or blank categories use Personal; a missing saved date uses the restore time.
