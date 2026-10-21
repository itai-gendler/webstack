---
kind: edge
routes:
  android: Android
steps:
- text: Type an address, keep or pick a tag, and save.
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
- text: Save the bookmark at once with an empty title, close the form and show the bookmark on Home.
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
      place: android::home
- text: Ask the website for its page title in the background; it does not answer, or has no title.
  kind: condition
  entities: []
  actor: user
  contexts:
    android:
      place: android::home
- text: Give the bookmark a title made from its domain, such as Github for github.com.
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

# Name a bookmark after its domain when the page gives no title

## Trigger

The User saves a new address, and the website does not answer or has no title.

## Outcome

The bookmark is already saved and on Home; it takes a title made from its domain, such as "Github" for github.com.
