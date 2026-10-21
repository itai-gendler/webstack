---
kind: alternate
routes:
  android: Android
steps:
- text: Enter a replacement tag name.
  kind: actor
  entities:
  - entity: tag
    effect: reads
    facts:
    - Name
  actor: user
  contexts:
    android:
      place: android::tags
- text: Rename the tag and its bookmark category assignments.
  kind: product
  entities:
  - entity: tag
    effect: changes
    facts:
    - Name
  - entity: bookmark
    effect: changes
    facts:
    - Category
  actor: user
  contexts:
    android:
      place: android::tags
---

# Rename a parked tag

## Trigger

The User renames a parked tag that is not the Fallback tag.

## Outcome

The tag stays parked under its new name, and every bookmark that had it carries the new name.
