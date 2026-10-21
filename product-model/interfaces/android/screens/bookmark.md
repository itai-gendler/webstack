---
entities:
- entity: bookmark
  shows:
  - URL
  - Title
  - Domain
  - Category
  collects:
  - URL
  - Title
  - Category
- entity: tag
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/WebsiteSheets.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/ItemOptionsSheet.kt
---

# Bookmark

One bookmark being saved or edited, and the options on a saved bookmark: open, edit, copy link, share, refresh its preview, select and delete. When saving, the User gives an address and a tag; when editing, also the title.
