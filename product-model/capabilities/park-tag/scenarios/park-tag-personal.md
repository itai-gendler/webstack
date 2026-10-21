---
kind: validation
routes:
  android: Android
steps:
- text: Request parking of the tag named Personal.
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
- text: Keep the default category active.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::tags
---

# Keep Personal on Home

## Trigger

The User tries to hide Personal from Home.

## Outcome

Personal stays on Home, and the app says it is the default tag and cannot be hidden.
