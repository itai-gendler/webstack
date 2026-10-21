---
kind: edge
routes:
  android: Android
steps:
- text: Submit a website address.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Find a bookmark with the same canonical address.
  kind: condition
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
    - Title
    - Domain
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Show the duplicate message and keep capture open.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
---

# Refuse a link that is already saved

## Trigger

The User saves an address that is the same link as a bookmark already saved.

## Outcome

Nothing is saved; New Bookmark stays open with "Link already in your stack", naming the saved bookmark by its title or domain.
