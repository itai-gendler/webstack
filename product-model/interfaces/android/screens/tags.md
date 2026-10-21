---
entities:
- entity: tag
  shows: &id001
  - Name
  - Position
  collects: *id001
- entity: preferences
  shows:
  - Fallback tag
  collects:
  - Fallback tag
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/CustomizeTagsSheet.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/dialogs/TagDialogs.kt
---

# Customize Tags

The active tags in their order, the parked (Hidden) tags, and the Fallback tag that receives the bookmarks of a deleted tag. Tags are added, renamed, reordered, parked, unparked and deleted here.
