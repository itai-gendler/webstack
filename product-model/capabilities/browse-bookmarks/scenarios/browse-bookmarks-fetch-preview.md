---
kind: alternate
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
- text: Read the enabled preview preference.
  kind: condition
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Fetch web previews
  actor: user
  contexts:
    android:
      place: android::home
- text: Fetch a preview of the website and keep it on the device.
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
---

# Cache a new website snapshot

## Trigger

With Fetch Web Previews on, the User browses a bookmark that has no preview on the device yet.

## Outcome

A preview of the website is fetched, kept on the device and shown again on later visits without fetching.
