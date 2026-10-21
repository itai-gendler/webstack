---
kind: primary
routes:
  android: Android
steps:
- text: Cancel the import review before insertion.
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
- text: Remove the import review and return to Backup & Restore.
  kind: product
  entities:
  - entity: import-review
    effect: removes
    from: Reviewing
  actor: user
  contexts:
    android:
      place: android::import
---

# Cancel a review before importing

## Trigger

The User chooses Cancel in Review Import before importing.

## Outcome

The review is discarded with all its selections and category choices, nothing is saved, and Backup & Restore is shown again.
