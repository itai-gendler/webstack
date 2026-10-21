---
kind: primary
routes:
  android: Android
steps:
- text: Enter a website address and choose a tag.
  kind: actor
  entities:
  - entity: tag
    effect: reads
    facts:
    - Name
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Trim the address, add https:// when it has no scheme, and save the bookmark with an empty title.
  kind: product
  entities:
  - entity: bookmark
    effect: creates
    facts:
    - URL
    - Title
    - Domain
    - Category
    - Saved at
    - Source folders
    - Preview
    - Selected
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Close the form and return to Home, where the new link is listed.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::home
- text: Fetch the page title in the background and give it to the bookmark.
  kind: product
  entities:
  - entity: bookmark
    effect: changes
    facts:
    - Title
  actor: user
  contexts:
    android:
      place: android::home
---

# Save a typed address

## Trigger

The User opens New Bookmark (also from the Add Link launcher shortcut), types an address and keeps or changes the tag.

## Outcome

The bookmark is saved under that tag with the current date, the form closes and it appears on Home; its title is filled in shortly after.
