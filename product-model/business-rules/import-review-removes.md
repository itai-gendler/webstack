---
appliesTo:
- type: entity
  id: import-review
  effect: removes
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#clearPendingPreprocessResult
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/ClusterApprovalSheet.kt#ClusterApprovalSheet
---

# The User closes their import review

The User's review closes when they cancel it or when its import completes.
