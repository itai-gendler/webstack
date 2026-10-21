---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#addCategory
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#parkCategory
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#unparkCategory
---

# Tag

A named category that bookmarks are filed under, such as the built-in Personal, Design, Tools, Work and Reading. The app calls them tags and categories.

## Information kept

- **Name** — The tag's name, unique ignoring case.
- **Position** — Its place in the order of the active tags, or of the parked tags.

## States

### Active

Shown on Home and offered wherever a tag is chosen.

### Parked

Hidden from Home, listed under Hidden in Customize Tags. Its bookmarks keep it and stay reachable under All and through search.
