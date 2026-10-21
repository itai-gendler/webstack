---
kind: primary
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
- text: Parse links, keep the first canonical occurrence, classify categories, and create the import review.
  kind: product
  entities:
  - entity: import-review
    effect: creates
    facts: &id001
    - Links
    - Suggested categories
    - Assigned categories
    - Included links
    - Duplicate count
    - Format notice
    - Progress
    to: Reviewing
  actor: user
  contexts:
    android:
      place: android::backup-restore
- text: Carry the user to the import review with all candidate links selected.
  kind: product
  entities:
  - entity: import-review
    effect: reads
    facts: *id001
  actor: user
  contexts:
    android:
      place: android::import
---

# Prepare browser bookmarks for review

## Trigger

In Backup & Restore, the User chooses Import Backup and picks a browser bookmark file (.html or .htm).

## Outcome

A review opens in Review Import with every link included, grouped by proposed tag, with the number of repeated links dropped from the file. Nothing is saved yet.

## Edge cases

- Files without a standard Netscape header can still reach review with a non-standard-format notice.
- Dates expressed in seconds, milliseconds, or microseconds are normalized; absent or nonpositive dates remain unknown.
- Folder names use the deepest meaningful folder after removing browser roots and generic names; ordinary numbered prefixes are cleaned.
