---
kind: edge
routes:
  android: Android
steps:
- text: Browse the bookmark.
  kind: actor
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
- text: Try to fetch a preview of the website.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
  actor: user
  contexts:
    android:
      place: android::home
- text: Show the bookmark with its title and domain instead of a preview.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Domain
    - Title
  actor: user
  contexts:
    android:
      place: android::home
---

# Keep browsing when no preview can be fetched

## Trigger

With Fetch Web Previews on, the User browses a bookmark without a preview, and no preview can be fetched.

## Outcome

The bookmark is shown with its title and domain instead, and stays fully usable.
