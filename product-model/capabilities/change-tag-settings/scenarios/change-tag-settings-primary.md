---
kind: primary
routes:
  android: Android
steps:
- text: Choose an active destination for deleted-category content.
  kind: actor
  entities:
  - entity: tag
    effect: reads
    facts:
    - Name
  actor: user
  contexts:
    android:
      place: android::tags
- text: Save the fallback destination in preferences.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Fallback tag
  actor: user
  contexts:
    android:
      place: android::tags
---

# Choose the Fallback tag

## Trigger

In Customize Tags, the User picks the tag that bookmarks move to when their tag is deleted.

## Outcome

The chosen tag is kept as the Fallback tag for later deletions.
