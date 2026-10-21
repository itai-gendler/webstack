---
kind: primary
routes:
  android: Android
steps:
- text: Choose a category and supply a search query.
  kind: actor
  entities:
  - entity: tag
    effect: reads
    facts:
    - Name
  actor: user
  contexts:
    android:
      place: android::home
- text: Filter bookmark content by the category and query and order it using preferences.
  kind: product
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - URL
    - Title
    - Domain
    - Category
    - Saved at
  - entity: preferences
    effect: reads
    facts:
    - Sort order
  actor: user
  contexts:
    android:
      place: android::home
- text: Read the matching bookmark content.
  kind: actor
  entities:
  - entity: bookmark
    effect: reads
    facts:
    - Title
    - URL
    - Domain
    - Category
    - Preview
  actor: user
  contexts:
    android:
      place: android::home
---

# Find saved websites

## Trigger

The User opens Home (or WebStack through its Search launcher shortcut), picks a tag and types a search.

## Outcome

Home lists the bookmarks with that tag that match the search, in the chosen order; clearing the search or choosing All widens the list.

## Edge cases

- An empty stack offers capture. No search matches offers clearing search; a category with no matches offers All.
- Parked categories do not appear in the category selector; their saved links remain reachable through All and search.

## Decision points

### Preview availability

What can the current item show?

- A local snapshot exists → show the cached snapshot.
- No snapshot exists and preview fetching is off → show the saved website identity without fetching a new snapshot.
