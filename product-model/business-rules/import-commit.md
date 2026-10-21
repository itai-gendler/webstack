---
appliesTo:
- type: capability
  id: review-import
- type: capability
  id: change-import-category
- type: capability
  id: select-import-links
- type: capability
  id: deselect-import-links
- type: capability
  id: import-bookmarks
- type: capability
  id: cancel-import
references:
- kind: spec
  role: intent
  target: spec_extracted.txt
  title: Bookmark import and export specification
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkImporter.kt#importBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/ClusterApprovalSheet.kt#ClusterApprovalSheet
---

# Nothing from a browser file is saved until the User confirms the import

Preparing and adjusting an import review changes no bookmark. Importing saves the included links under the tags assigned at that moment, as one batch: if the batch fails, none of its links is saved and the review stays open.
