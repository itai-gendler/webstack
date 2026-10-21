---
appliesTo:
- type: capability
  id: export-backup
- type: capability
  id: review-import
references:
- kind: spec
  role: intent
  target: spec_extracted.txt
  title: Bookmark import and export specification
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkExporter.kt#exportBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/data/WebsiteDao.kt#byCategory
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkNormalizer.kt#normalizeToMillis
---

# An HTML export puts each tag's bookmarks in a folder of that name

Tags are written as folders in name order, each with its bookmarks newest first; Uncategorized bookmarks go at the top level. A blank title is written as the address, and an unknown saved date as the export time. Dates are written in seconds; a browser import reads seconds, milliseconds or microseconds.
