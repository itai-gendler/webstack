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
  target: app/src/main/java/com/example/ui/sheets/SettingsSheet.kt#SettingsBottomSheetContent
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#exportBackup
- kind: code
  role: implementation
  target: app/src/main/java/com/example/data/BackupManager.kt#exportToJson
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkExporter.kt#exportBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkDelivery.kt#exportToSaf
domain: backup-restore
---

# Export backup

Write the saved stack to a chosen document as a WebStack backup, JSON backup, or browser-compatible HTML file.
