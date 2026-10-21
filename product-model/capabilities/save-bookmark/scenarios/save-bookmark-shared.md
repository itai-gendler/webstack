---
kind: alternate
routes:
  android: Android
steps:
- text: Share text containing a website address to the app.
  kind: actor
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Extract the first supported address from the shared text and prefill capture.
  kind: product
  entities: []
  actor: user
  contexts:
    android:
      place: android::bookmark
- text: Confirm the proposed address and tag.
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
- text: Create the bookmark and return to the stack while its title is fetched.
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
- text: Fetch the page title after capture and change the bookmark title, using a domain-derived fallback when needed.
  kind: product
  actor: user
  entities:
  - entity: bookmark
    effect: changes
    facts:
    - Title
  contexts:
    android:
      place: android::home
---

# Save an Android-shared link

## Trigger

The User shares text from another app, such as a browser, to WebStack.

## Outcome

New Bookmark opens with the first link found in the text, and it is saved under the tag the User picks.

## Edge cases

- If no address can be extracted, the nonblank shared text is offered for editing before saving.
