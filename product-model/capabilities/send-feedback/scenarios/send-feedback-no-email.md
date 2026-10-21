---
kind: edge
routes:
  android: Android
steps:
- text: Choose Send Email.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
- text: Report the missing email application.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
---

# Report a missing email application

## Trigger

Neither email hand-off can be opened.

## Outcome

The app reports that no email app was found and shows the contact destination.
