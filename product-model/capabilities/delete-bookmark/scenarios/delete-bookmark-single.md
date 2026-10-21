---
kind: primary
routes:
  android: Android
steps:
- text: Confirm deletion of the bookmark.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Title
    - URL
    - Selected
  actor: user
  contexts:
    android:
      place: android::home
- text: Remove each confirmed bookmark and its cached snapshot.
  kind: product
  entities:
  - entity: bookmark
    effect: removes
  actor: user
  contexts:
    android:
      place: android::home
---

# Delete a bookmark

## Trigger

The User chooses Delete in a bookmark's options and confirms.

## Outcome

The bookmark and its cached preview are removed from the device.
