---
kind: validation
routes:
  android: Android
steps:
- text: Leave the address empty.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Keep the capture form without saving.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
---

# Save nothing without an address

## Trigger

The address in New Bookmark is empty or only spaces.

## Outcome

Saving is unavailable and nothing is saved.
