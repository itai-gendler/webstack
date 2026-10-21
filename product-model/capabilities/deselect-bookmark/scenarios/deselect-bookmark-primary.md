---
kind: primary
routes:
  android: Android
steps:
- text: Deselect a bookmark or cancel the current selection.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Selected
  actor: user
  contexts:
    android:
      place: android::home
- text: Clear the selected status of the affected bookmark; clearing all items returns to ordinary browsing.
  kind: product
  entities:
  - entity: bookmark
    effect: changes
    facts:
    - Selected
  actor: user
  contexts:
    android:
      place: android::home
---

# Deselect bookmarks

## Trigger

While bookmarks are selected, the User taps a selected bookmark again or cancels the selection.

## Outcome

That bookmark leaves the selection; cancelling, or deselecting the last one, returns Home to ordinary browsing.
