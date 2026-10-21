---
kind: primary
result: achieved
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
  capability: review-import
- text: Create the import review and carry the user to its review process.
  kind: product
  entities:
  - entity: import-review
    effect: creates
    facts:
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
      place: android::import
  capability: review-import
- text: Change a proposed group’s assigned category.
  kind: actor
  entities:
  - entity: import-review
    effect: reads
    facts:
    - Suggested categories
    - Assigned categories
  actor: user
  contexts:
    android:
      place: android::import
  capability: change-import-category
- text: Keep the chosen destination in the import review.
  kind: product
  entities:
  - entity: import-review
    effect: changes
    facts:
    - Assigned categories
  actor: user
  contexts:
    android:
      place: android::import
  capability: change-import-category
- text: Confirm the included import review links.
  kind: actor
  entities:
  - entity: import-review
    effect: reads
    facts:
    - Included links
    - Assigned categories
  actor: user
  contexts:
    android:
      place: android::import
  capability: import-bookmarks
- text: Start processing the import review.
  kind: product
  entities:
  - entity: import-review
    effect: changes
    facts:
    - Progress
    from: Reviewing
    to: Importing
  actor: user
  contexts:
    android:
      place: android::import
  capability: import-bookmarks
- text: Create the new bookmark and any missing active tag.
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
  - entity: tag
    effect: creates
    facts:
    - Name
    - Position
    to: Active
  actor: user
  contexts:
    android:
      place: android::import
  capability: import-bookmarks
- text: Remove the completed import review, report counts, and return to Settings.
  kind: product
  entities:
  - entity: import-review
    effect: removes
    from: Importing
  actor: user
  contexts:
    android:
      place: android::settings
  capability: import-bookmarks
---

# Import with a group sent to another tag

## Trigger

In Backup & Restore, the User chooses Import Backup and picks a browser bookmark file.

## Outcome

The included new links are saved, the reassigned group under the tag the User chose; links already saved are skipped, and the review closes.
