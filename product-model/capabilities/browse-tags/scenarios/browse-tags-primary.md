---
kind: primary
routes:
  android: Android
steps:
- text: Open the category customization view.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::tags
- text: Present tag names and active order, parked categories, and the fallback preferences.
  kind: product
  entities:
  - entity: tag
    effect: reads
    facts:
    - Name
    - Position
  - entity: preferences
    effect: reads
    facts:
    - Fallback tag
  actor: user
  contexts:
    android:
      place: android::tags
---

# See all tags

## Trigger

The User opens Customize Tags from Appearance.

## Outcome

The active tags appear in their order beside the parked ones, together with the Fallback tag that receives the bookmarks of a deleted tag.
