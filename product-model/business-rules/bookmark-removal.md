---
appliesTo:
- type: entity
  id: bookmark
  effect: removes
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
---

# The User deletes bookmarks

A confirmed deletion, of one bookmark or of a selection, removes those bookmarks.
