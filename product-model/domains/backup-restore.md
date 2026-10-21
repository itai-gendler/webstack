---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/SettingsSheet.kt
---

# Backup & Restore

File transfer and review of incoming browser bookmarks.

## Boundary

Owns file export, restoration, and pending import review. It does not own ordinary capture from typed or shared addresses.
