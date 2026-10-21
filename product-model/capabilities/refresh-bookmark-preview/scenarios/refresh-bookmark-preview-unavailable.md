---
kind: edge
routes:
  android: Android
steps:
- text: Refresh the bookmark snapshot.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Preview
  actor: user
  contexts:
    android:
      place: android::home
- text: Discard the old preview and try to fetch a new one.
  kind: product
  entities:
  - entity: bookmark
    effect: changes
    facts:
    - Preview
  actor: user
  contexts:
    android:
      place: android::home
- text: Show the bookmark with its title and domain when no preview can be fetched.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Title
    - Domain
  actor: user
  contexts:
    android:
      place: android::home
---

# Refresh when no new preview can be fetched

## Trigger

The User refreshes a bookmark's preview with Fetch Web Previews on, and no new preview can be fetched.

## Outcome

The bookmark is shown with its title and domain instead, and stays fully usable.
