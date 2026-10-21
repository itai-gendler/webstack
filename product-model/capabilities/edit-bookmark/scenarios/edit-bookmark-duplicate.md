---
kind: edge
routes:
  android: Android
steps:
- text: Submit an edited bookmark address.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Find another saved item with the proposed canonical address.
  kind: condition
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Report the conflict without applying the edit.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
---

# Refuse an edit that matches another bookmark

## Trigger

The User changes a bookmark's address to one that is the same link as another bookmark.

## Outcome

The edit stays open with "Link already in your stack", naming the other bookmark; nothing is saved.
