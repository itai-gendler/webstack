---
appliesTo:
- type: entity
  id: import-review
  effect: creates
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#preprocessHtmlBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/ClusterApprovalSheet.kt#ClusterApprovalSheet
---

# The User starts an import review

Choosing a browser bookmark file in Backup & Restore prepares a review for the User.
