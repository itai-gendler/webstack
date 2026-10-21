---
appliesTo:
- type: entity
  id: bookmark
  effect: changes
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#updateWebsite
---

# The User changes bookmarks

The User edits a bookmark's title, address and tag, and selects bookmarks for bulk actions. Fetching a new preview also needs Fetch Web Previews on.
