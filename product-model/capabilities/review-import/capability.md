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
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#preprocessHtmlBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkImporter.kt#preprocess
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkParser.kt#parse
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/DomainClassifier.kt#classifyAll
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/FolderCleaner.kt#cleanFolderName
domain: backup-restore
---

# Review import

Prepare a browser bookmark file for a separate confirmation. Parsing keeps link titles, dates, and source folders; duplicate addresses within the file are reduced to their first occurrence before category suggestions are formed.

Browser import accepts HTTP and HTTPS website links. The original URL is retained for each accepted link; canonical comparison decides which occurrences are duplicates.
