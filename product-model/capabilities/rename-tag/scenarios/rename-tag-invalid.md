---
kind: validation
routes:
  android: Android
steps:
- text: Request a tag rename.
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
- text: Keep the current name and explain that it cannot be used.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::tags
---

# Refuse a rename

## Trigger

The User proposes a blank name, All, Personal or a name another tag already has, or tries to rename Personal.

## Outcome

The tag keeps its name and its bookmarks are unchanged; the app says the name is invalid or taken.
