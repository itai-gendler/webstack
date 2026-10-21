---
kind: primary
routes:
  android: Android
steps:
- text: Change the card detail and sort preferences.
  kind: actor
  entities:
  - entity: preferences
    effect: reads
    facts:
    - Show domain
    - Show tags
    - Sort order
  actor: user
  contexts:
    android:
      place: android::card-details
- text: Keep the visibility and ordering choices in preferences.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Show domain
    - Show tags
    - Sort order
  actor: user
  contexts:
    android:
      place: android::card-details
---

# Choose card details and order

## Trigger

The User turns the domain or tag line on cards on or off, or switches between newest first and oldest first, in Card Details.

## Outcome

Home shows the chosen details in the chosen order, and the choices are kept for later launches.
