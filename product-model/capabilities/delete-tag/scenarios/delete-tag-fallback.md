---
kind: alternate
routes:
  android: Android
steps:
- text: Confirm deletion of the fallback tag.
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
- text: Choose a remaining destination and save the preferences.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Fallback tag
  actor: user
  contexts:
    android:
      place: android::tags
- text: Move bookmark assignments to the replacement and remove the tag.
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

# Delete the Fallback tag itself

## Trigger

The User deletes the tag that is currently the Fallback tag.

## Outcome

The first remaining active tag (Personal if none is left) becomes the Fallback tag and receives the deleted tag's bookmarks.
