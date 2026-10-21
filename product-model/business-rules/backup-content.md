---
appliesTo:
- type: capability
  id: export-backup
- type: capability
  id: restore-backup
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/data/BackupManager.kt#exportToJson
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#exportBackup
---

# A backup carries bookmarks and active tags, and restoring it only adds

WebStack (.webstack) and JSON backups hold the same content: each bookmark's address, title, domain, tag and saved date, plus the active tags. Previews, parked tags, original browser folders and preferences are not in a backup. Restoring merges: it adds what is missing and never removes or overwrites anything already on the device.
