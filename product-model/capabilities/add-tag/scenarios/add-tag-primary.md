---
kind: primary
routes:
  android: Android
steps:
- text: Enter a new category name.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::tags
- text: Trim the name and create the tag at the end of the active order.
  kind: product
  entities:
  - entity: tag
    effect: creates
    facts:
    - Name
    - Position
    to: Active
  actor: user
  contexts:
    android:
      place: android::tags
---

# Add a tag

## Trigger

The User enters a new tag name in Customize Tags, or chooses New Tag while saving or editing a bookmark.

## Outcome

The trimmed name becomes an active tag at the end of the tag order and is offered wherever a tag is chosen.
