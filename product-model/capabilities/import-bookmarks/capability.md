---
availability:
- place: android
references:
- kind: spec
  role: intent
  target: spec_extracted.txt
  title: Bookmark import and export specification
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/ClusterApprovalSheet.kt#ClusterApprovalSheet
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#commitImportBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkImporter.kt#importBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/SettingsSheet.kt#SettingsBottomSheetContent
domain: backup-restore
---

# Import bookmarks

Import the included links of a pending review under their assigned tags. Progress is shown while importing, then how many links were imported and how many were already saved.
