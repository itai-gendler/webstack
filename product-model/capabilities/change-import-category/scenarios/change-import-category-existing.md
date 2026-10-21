---
kind: primary
routes:
  android: Android
steps:
- text: Choose an existing destination tag for a group.
  kind: actor
  entities:
  - entity: import-review
    effect: reads
    facts:
    - Suggested categories
    - Assigned categories
  - entity: tag
    effect: reads
    facts:
    - Name
  actor: user
  contexts:
    android:
      place: android::import
- text: Keep the chosen destination in the import review assignments.
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

# Send a group to an existing tag

## Trigger

In Review Import, the User picks one of their tags for a proposed group.

## Outcome

Every link of the group will be imported under that tag; nothing is saved until the User imports.
