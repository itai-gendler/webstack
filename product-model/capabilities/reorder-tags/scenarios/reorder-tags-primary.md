---
kind: primary
routes:
  android: Android
steps:
- text: Move an active tag to another position.
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
- text: Persist the changed tag positions for later category selection.
  kind: product
  entities:
  - entity: tag
    effect: changes
    facts:
    - Position
  actor: user
  contexts:
    android:
      place: android::tags
---

# Reorder tags

## Trigger

In Customize Tags, the User drags an active tag or uses Move Up or Move Down.

## Outcome

The new order is kept and used on Home and wherever a tag is chosen; the first tag becomes the one a new bookmark starts with.
