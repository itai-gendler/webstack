---
kind: primary
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
- text: Return a parked built-in tag to active use.
  kind: product
  entities:
  - entity: tag
    effect: changes
    facts:
    - Position
    from: Parked
    to: Active
  actor: user
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

# Restore the built-in tag order

## Trigger

The User, whose tags are only the built-in ones, has reordered them and parked some, and confirms Reset Defaults.

## Outcome

Personal, Design, Tools, Work and Reading are active in that order, and Personal is the Fallback tag.
