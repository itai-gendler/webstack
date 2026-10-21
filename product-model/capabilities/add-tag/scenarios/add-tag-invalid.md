---
kind: validation
routes:
  android: Android
steps:
- text: Submit a proposed category name.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::tags
- text: Keep the existing tag names and report the invalid input.
  kind: product
  entities:
  - entity: tag
    effect: reads
    facts:
    - Name
  actor: user
  contexts:
    android:
      place: android::tags
---

# Refuse a name that is blank, reserved or taken

## Trigger

The User proposes a name that is blank, All, or already used by an active or parked tag (Personal always is), ignoring case.

## Outcome

No tag is added, and the app says the tag already exists or is invalid.
