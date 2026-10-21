---
kind: primary
routes:
  android: Android
steps:
- text: Park an active tag.
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
- text: Keep the tag as parked and remove it from active category choices.
  kind: product
  entities:
  - entity: tag
    effect: changes
    facts:
    - Position
    from: Active
    to: Parked
  actor: user
  contexts:
    android:
      place: android::tags
---

# Park a tag

## Trigger

In Customize Tags, the User chooses Hide from Home on an active tag other than Personal.

## Outcome

The tag moves to the parked (Hidden) tags and leaves the tag choices on Home; its bookmarks keep the tag and stay reachable under All and through search.
