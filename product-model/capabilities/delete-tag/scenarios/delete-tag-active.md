---
kind: primary
routes:
  android: Android
steps:
- text: Confirm deletion of the tag.
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
- text: Read which category is set as the fallback in preferences.
  kind: product
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Fallback tag
  actor: user
  contexts:
    android:
      place: android::tags
- text: Move the tag's bookmarks to the Fallback tag and remove the tag.
  kind: product
  entities:
  - entity: bookmark
    effect: changes
    facts:
    - Category
  - entity: tag
    effect: removes
    from: Active
  actor: user
  contexts:
    android:
      place: android::tags
---

# Delete an active tag

## Trigger

The User deletes an active tag other than Personal and confirms.

## Outcome

The tag is gone, and every bookmark that had it now has the Fallback tag; no bookmark is lost.
