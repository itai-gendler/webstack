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
  actor: user
  contexts:
    android:
      place: android::import
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
- text: Roll back the failed insertion and return the import review to reviewable state.
  kind: product
  entities:
  - entity: import-review
    effect: changes
    facts:
    - Progress
    from: Importing
    to: Reviewing
  actor: user
  contexts:
    android:
      place: android::import
---

# Return to review after an insertion failure

## Trigger

The selected browser-bookmark batch fails during insertion.

## Outcome

None of that batch’s new links is committed. The error is shown and the pending choices can be retried.
