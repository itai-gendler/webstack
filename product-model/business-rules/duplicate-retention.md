---
appliesTo:
- type: capability
  id: save-bookmark
- type: capability
  id: edit-bookmark
- type: capability
  id: review-import
- type: capability
  id: import-bookmarks
- type: capability
  id: restore-backup
references:
- kind: spec
  role: intent
  target: spec_extracted.txt
  title: Bookmark import and export specification
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#findDuplicateUrl
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkImporter.kt#preprocess
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkImporter.kt#importBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#restoreBackup
---

# A link already saved is never saved twice

Saving or editing a link that matches another bookmark is refused with "Link already in your stack", naming the bookmark it matches. A browser import keeps the first of repeated links in its file and skips links already saved. Restoring a backup adds only links not already saved and leaves existing bookmarks as they are.
