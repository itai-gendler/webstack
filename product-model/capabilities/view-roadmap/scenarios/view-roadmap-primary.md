---
kind: primary
routes:
  android: Android
steps:
- text: Open Roadmap.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::roadmap
- text: Present PC Companion Mode as an idea under consideration.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::roadmap
---

# Read the roadmap

## Trigger

The User opens Roadmap from App Info.

## Outcome

PC Companion Mode is shown as an idea still being thought through, not an available feature, beside feedback and sponsorship links.
