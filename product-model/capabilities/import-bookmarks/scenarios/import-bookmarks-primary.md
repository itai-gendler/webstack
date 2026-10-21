---
kind: primary
routes:
  android: Android
steps:
- text: Confirm the included links and category assignments in the import review.
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
- text: Move the import review into processing.
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
- text: Add each new bookmark while preserving imported titles, dates, and source folders.
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
      place: android::import
- text: Create missing active tag names from the selected assignments.
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
      place: android::import
- text: Report imported and skipped counts, remove the import review, and return to Settings.
  kind: product
  entities:
  - entity: import-review
    effect: removes
    from: Importing
  actor: user
  contexts:
    android:
      place: android::settings
---

# Commit selected browser bookmarks

## Trigger

The user has at least one selected link in Review Import and chooses Import.

## Outcome

The included new links are saved under their assigned tags, with their titles, dates and original folders; links already saved are skipped and counted. Tags that did not exist yet are added, the review closes, and Settings shows the imported and skipped counts.
