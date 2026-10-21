---
kind: primary
routes:
  android: Android
steps:
- text: Edit the bookmark title and address and choose its category.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Title
    - URL
    - Category
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Save the bookmark changes and close editing.
  kind: product
  entities:
  - entity: bookmark
    effect: changes
    facts:
    - Title
    - URL
    - Domain
    - Category
  actor: user
  contexts:
    android:
      place: android::bookmark
---

# Edit a bookmark

## Trigger

The User chooses Edit in a bookmark's options, changes its title, address or tag, and saves.

## Outcome

The title and address are trimmed, https:// is added to an address without a scheme, and the changes are saved; the bookmark keeps its saved date and original browser folders.

## Edge cases

- Both title and address must be nonblank before Save Changes becomes available.
