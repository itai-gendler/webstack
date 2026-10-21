---
appliesTo:
- type: entity
  id: bookmark
  effect: creates
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#commitImportBookmarks
---

# The User creates bookmarks

Saving a link, confirming a browser import and restoring a backup create bookmarks for the device's User.
