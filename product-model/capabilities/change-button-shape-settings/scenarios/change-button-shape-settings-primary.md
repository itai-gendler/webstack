---
kind: primary
routes:
  android: Android
steps:
- text: Choose an add-button shape.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::button-shape
- text: Keep the button shape in preferences for subsequent use.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Button shape
  actor: user
  contexts:
    android:
      place: android::button-shape
---

# Choose an add-button shape

## Trigger

The User picks one of the twelve shapes in Button Shape.

## Outcome

The add button takes that shape, and the choice is kept for later launches.
