---
kind: primary
routes:
  android: Android
steps:
- text: Return a parked tag to active use.
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
- text: Make the tag active at the chosen position, or append it when no position is chosen.
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
---

# Unpark a tag

## Trigger

In Customize Tags, the User chooses Show on Home on a parked tag, or drags it back among the active tags.

## Outcome

The tag is active again, at the place it was dropped or at the end of the order, and is offered on Home.
