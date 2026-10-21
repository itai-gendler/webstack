---
actors:
- user
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
  target: app/src/main/java/com/example/ui/sheets/ClusterApprovalSheet.kt#ClusterApprovalSheet
---

# Import browser bookmarks

## Goal

Bring an existing browser collection into the stack with reviewed categories and selections.

## Success criterion

The included new links are saved under the reviewed categories, existing links survive, and import results are reported.
