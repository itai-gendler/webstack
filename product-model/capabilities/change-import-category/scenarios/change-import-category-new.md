---
kind: alternate
routes:
  android: Android
steps:
- text: Enter a new nonblank destination name for a group.
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
- text: Trim the name and keep it in the import review assignments; it becomes an active category when selected
    links are committed.
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
---

# Send a group to a new tag

## Trigger

In Review Import, the User chooses to name a new tag for a proposed group.

## Outcome

The group carries the new name in the review; the tag is created only when the import is confirmed.
