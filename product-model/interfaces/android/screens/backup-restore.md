---
entities:
- entity: bookmark
  shows:
  - URL
  - Title
  - Category
  - Saved at
- entity: tag
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/BackupRestoreSheet.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/SettingsSheet.kt
---

# Backup & Restore

The number of saved links, the three export formats with what each is for, and restoring from a .webstack, .json, .html or .htm file.
