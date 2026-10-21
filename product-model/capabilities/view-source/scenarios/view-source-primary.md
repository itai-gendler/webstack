---
kind: primary
routes:
  android: Android
steps:
- text: Choose View source code.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
- text: Hand the source repository destination to Android.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
---

# Open the source code

## Trigger

The User chooses View source code in App Info.

## Outcome

The project's GitHub repository opens in the browser.
