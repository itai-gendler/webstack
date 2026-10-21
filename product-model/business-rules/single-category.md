---
appliesTo:
- type: entity
  id: bookmark
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/WebsiteSheets.kt#EditWebsiteSheetContent
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#parkCategory
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#deleteCategory
---

# Each bookmark has exactly one tag

Choosing another tag for a bookmark replaces its previous one. Parking a tag leaves its bookmarks under it; deleting a tag moves its bookmarks to the Fallback tag.
