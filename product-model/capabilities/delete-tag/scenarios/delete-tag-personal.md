---
kind: validation
routes:
  android: Android
steps:
- text: Request deletion of the tag named Personal.
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
- text: Explain that the default category cannot be deleted.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::tags
---

# Keep Personal

## Trigger

The User tries to delete Personal.

## Outcome

Personal stays: it is the default tag and cannot be deleted.
