---
kind: primary
routes:
  android: Android
steps:
- text: Choose a bookmark to open.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts: &id001
    - URL
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Hand the bookmark URL to the Android browser handler.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts: *id001
  actor: user
  contexts:
    android:
      place: android::bookmark
---

# Open a bookmark

## Trigger

The User taps a bookmark on Home.

## Outcome

The saved address opens in the browser Android chooses.
