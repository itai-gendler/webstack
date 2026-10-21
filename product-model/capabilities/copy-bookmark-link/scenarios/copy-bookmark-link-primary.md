---
kind: primary
routes:
  android: Android
steps:
- text: Choose Copy Link for the bookmark.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts: &id001
    - URL
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Copy the bookmark URL and show confirmation.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts: *id001
  actor: user
  contexts:
    android:
      place: android::bookmark
---

# Copy a bookmark's link

## Trigger

The User chooses Copy Link on a bookmark.

## Outcome

The bookmark's address is on the Android clipboard and a confirmation is shown.
