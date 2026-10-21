---
kind: primary
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

# Rename an active tag

## Trigger

The User renames an active tag other than Personal that is not the Fallback tag.

## Outcome

The tag and every bookmark that had it carry the new name; the Fallback tag is unchanged.
