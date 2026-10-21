---
kind: primary
routes:
  android: Android
steps:
- text: Dismiss the release introduction.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::whats-new
- text: Record the acknowledged release in preferences and reveal the stack.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Seen release
  actor: user
  contexts:
    android:
      place: android::whats-new
---

# Dismiss the release introduction

## Trigger

The User dismisses the release introduction shown at launch.

## Outcome

Home is shown, and the introduction does not open by itself again for this release.
