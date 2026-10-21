---
kind: alternate
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
- text: Open an email composer with the developer destination and an app-version subject; if that hand-off fails,
    try a basic email link.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
---

# Give feedback by email

## Trigger

The User chooses Send Email.

## Outcome

An email to the developer opens in the User's email app, with the app version in the subject.
