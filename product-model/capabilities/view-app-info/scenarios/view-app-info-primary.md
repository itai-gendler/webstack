---
kind: primary
routes:
  android: Android
steps:
- text: Open App Info.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
- text: Show the application version and attribution.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
---

# See app info

## Trigger

The User opens App Info from Settings.

## Outcome

The installed version and the author are shown, with the way to What's New, WebStack Features, Roadmap, the source code, feedback and sponsorship.
