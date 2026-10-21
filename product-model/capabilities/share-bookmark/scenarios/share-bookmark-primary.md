---
kind: primary
routes:
  android: Android
steps:
- text: Choose Share for the bookmark.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts: &id001
    - URL
    - Title
    - Domain
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Offer the bookmark title, or its domain when the title is blank, together with its URL to Android sharing.
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

# Share a bookmark

## Trigger

The User chooses Share on a bookmark.

## Outcome

Android sharing opens with the bookmark's title (or its domain when it has none) and its address.
