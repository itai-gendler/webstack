---
kind: primary
routes:
  android: Android
steps:
- text: Choose Sponsor.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
- text: Open the external sponsorship page; any sponsorship is completed there.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::app-info
---

# Sponsor the project

## Trigger

The User chooses Sponsor in App Info or Roadmap.

## Outcome

The developer's GitHub Sponsors page opens in the browser; any sponsorship happens there.
