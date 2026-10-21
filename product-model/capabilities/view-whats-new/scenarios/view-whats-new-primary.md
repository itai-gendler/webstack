---
kind: primary
routes:
  android: Android
steps:
- text: Read the release introduction.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::whats-new
- text: Present the current release highlights.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::whats-new
---

# Read what's new

## Trigger

The release introduction opens at launch until it is dismissed, or the User opens What's New from App Info.

## Outcome

The highlights of the current release are shown.
