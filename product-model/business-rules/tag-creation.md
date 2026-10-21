---
appliesTo:
- type: entity
  id: tag
  effect: creates
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#addCategory
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#commitImportBookmarks
---

# The User creates tags

The User adds tags in Customize Tags or while saving or editing a bookmark; confirming an import or restoring a backup adds the tags it brings that do not exist yet.
