---
kind: alternate
routes:
  android: Android
steps:
- text: Confirm the displayed number of selected bookmarks.
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

# Delete the selected bookmarks

## Trigger

With bookmarks selected, the User chooses to delete them and confirms the number shown.

## Outcome

Every selected bookmark and its cached preview are removed, and Home leaves selection mode.
