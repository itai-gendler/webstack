---
appliesTo:
- type: entity
  id: import-review
  effect: changes
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#commitImportBookmarks
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/ClusterApprovalSheet.kt#ClusterApprovalSheet
---

# The User changes their import review

The User includes and leaves out links, and assigns groups to tags, in their own import review.
