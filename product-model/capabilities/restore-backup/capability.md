---
availability:
- place: android
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#restoreBackup
- kind: code
  role: implementation
  target: app/src/main/java/com/example/data/BackupManager.kt#parseBackup
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/SettingsSheet.kt#SettingsBottomSheetContent
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
domain: backup-restore
---

# Restore backup

Merge an application backup into the existing stack. Restore is available from the file picker or by opening a WebStack backup in Android.
