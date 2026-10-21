---
kind: edge
routes:
  android: Android
steps:
- text: Confirm the included links in the import review.
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
- text: Process the import review and compare existing bookmark addresses.
  kind: product
  entities:
  - entity: import-review
    effect: changes
    facts:
    - Progress
    from: Reviewing
    to: Importing
  - entity: bookmark
    effect: reads
    facts:
    - URL
  actor: user
  contexts:
    android:
      place: android::import
- text: Close the import review and report zero insertions.
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

# Skip links already saved

## Trigger

Every included link already has a canonical match in the saved stack, and all assigned category names are already active.

## Outcome

No saved links change; the result reports zero inserted and the skipped-duplicate count.
