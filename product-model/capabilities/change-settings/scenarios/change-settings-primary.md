---
kind: primary
routes:
  android: Android
steps:
- text: Change the Fetch Web Previews preference.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::settings
- text: Keep the preview-fetching choice in preferences.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Fetch web previews
  actor: user
  contexts:
    android:
      place: android::settings
---

# Turn web previews on or off

## Trigger

The User switches Fetch Web Previews in Settings.

## Outcome

The choice is kept; while it is off, no new previews are fetched and previews already on the device stay visible.
