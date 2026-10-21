---
kind: primary
routes:
  android: Android
steps:
- text: Choose a theme and presentation preference.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::appearance
- text: Persist the selected theme and layout in preferences.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Theme
    - Layout
  actor: user
  contexts:
    android:
      place: android::appearance
---

# Choose theme and layout

## Trigger

The User chooses a theme (system, light or dark) or a layout (cards, grid or list) in Appearance.

## Outcome

The choice is kept on the device and applies to Home from then on.
