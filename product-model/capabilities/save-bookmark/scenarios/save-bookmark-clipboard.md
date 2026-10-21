---
kind: alternate
routes:
  android: Android
steps:
- text: Open capture with its address field empty.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Offer the first recognized address from clipboard content.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Use the clipboard suggestion and confirm a tag.
  kind: actor
  entities:
  - entity: tag
    effect: reads
    facts:
    - Name
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Create the bookmark and close capture.
  kind: product
  entities:
  - entity: bookmark
    effect: creates
    facts:
    - URL
    - Title
    - Domain
    - Category
    - Saved at
    - Source folders
    - Preview
    - Selected
  actor: user
  contexts:
    android:
      place: android::home
- text: Fetch the page title after capture and change the bookmark title, using a domain-derived fallback when needed.
  kind: product
  actor: user
  entities:
  - entity: bookmark
    effect: changes
    facts:
    - Title
  contexts:
    android:
      place: android::home
---

# Save a clipboard suggestion

## Trigger

The User opens New Bookmark with its address empty while a link is on the Android clipboard.

## Outcome

The link is offered as a suggestion and saved only once the User takes it and saves.
