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
- text: Carry the fallback destination in preferences to the renamed category.
  kind: product
  actor: user
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Fallback tag
  contexts:
    android:
      place: android::tags
---

# Rename the Fallback tag

## Trigger

The User renames the tag that is currently the Fallback tag.

## Outcome

The tag, its bookmarks and the Fallback tag setting all carry the new name.
