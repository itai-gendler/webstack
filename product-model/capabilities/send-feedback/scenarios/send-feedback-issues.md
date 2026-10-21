---
kind: primary
routes:
  android: Android
steps:
- text: Choose GitHub Issues or Feature Requests.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
- text: Open the project issue page in an external browser.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
---

# Give feedback on GitHub

## Trigger

The User chooses GitHub Issues under Feedback in App Info, or Feature Requests in Roadmap.

## Outcome

The project's GitHub issues open in the browser; the feedback itself is written there.
