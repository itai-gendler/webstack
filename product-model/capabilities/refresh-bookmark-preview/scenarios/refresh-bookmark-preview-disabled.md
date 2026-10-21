---
kind: validation
routes:
  android: Android
steps:
- text: Request a preview refresh for the bookmark.
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
- text: Read the disabled preference.
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
- text: Explain the settings prerequisite without starting a refresh.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::home
---

# Ask for web previews before refreshing

## Trigger

The User asks to refresh a bookmark's preview while Fetch Web Previews is off.

## Outcome

The app says to enable web previews in Settings, and the preview stays as it was.
