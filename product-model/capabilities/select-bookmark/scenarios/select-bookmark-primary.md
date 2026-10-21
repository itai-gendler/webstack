---
kind: primary
routes:
  android: Android
steps:
- text: Select a bookmark, then add further items to the selection.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Title
    - URL
  actor: user
  contexts:
    android:
      place: android::home
- text: Mark the bookmark selected and show the selection count and order.
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

# Select bookmarks

## Trigger

The User long-presses a bookmark and chooses Select, then taps further bookmarks.

## Outcome

Each bookmark joins the selection with its position number, and the selected count is shown, ready for bulk deletion.
