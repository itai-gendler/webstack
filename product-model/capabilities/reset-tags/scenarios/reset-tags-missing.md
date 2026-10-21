---
kind: alternate
routes:
  android: Android
steps:
- text: Confirm resetting the built-in tag arrangement.
  kind: actor
  entities:
  - entity: tag
    effect: reads
    facts:
    - Name
    - Position
  actor: user
  contexts:
    android:
      place: android::tags
- text: Create the missing built-in tag in active use.
  kind: product
  actor: user
  entities:
  - entity: tag
    effect: creates
    facts:
    - Name
    - Position
    to: Active
  contexts:
    android:
      place: android::tags
- text: Restore the default tag order and deletion preferences.
  kind: product
  entities:
  - entity: tag
    effect: changes
    facts:
    - Position
  - entity: preferences
    effect: changes
    facts:
    - Fallback tag
  actor: user
  contexts:
    android:
      place: android::tags
---

# Bring back a deleted built-in tag

## Trigger

The User, who has deleted a built-in tag other than Personal and has no tags of their own, confirms Reset Defaults.

## Outcome

The deleted built-in tag is back, the built-in order is restored and Personal is the Fallback tag; bookmarks keep the tags they have.
