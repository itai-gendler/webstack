---
kind: alternate
routes:
  android: Android
steps:
- text: Cancel the deletion confirmation.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::home
- text: Keep the bookmark content.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
    - Title
  actor: user
  contexts:
    android:
      place: android::home
---

# Cancel a deletion

## Trigger

The User cancels the deletion confirmation.

## Outcome

Every bookmark stays as it was.
