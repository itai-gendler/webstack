---
entities:
- entity: import-review
  shows:
  - Links
  - Suggested categories
  - Assigned categories
  - Included links
  - Duplicate count
  - Format notice
  - Progress
  collects:
  - Assigned categories
  - Included links
- entity: tag
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/ClusterApprovalSheet.kt
---

# Review Import

The pending import: the proposed groups with their assigned tags, link counts and sample domains, the links of each group (the first 40 listed one by one), how many repeated links were dropped from the file, a notice when the file is not a standard browser export, the number of links included, and progress while importing.
