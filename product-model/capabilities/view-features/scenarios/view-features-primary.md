---
kind: primary
routes:
  android: Android
steps:
- text: Open WebStack Features.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::features
- text: Present the shipped feature explanations.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::features
---

# Read the feature guide

## Trigger

The User opens WebStack Features from App Info.

## Outcome

Each feature is explained with where to find it in the app.
