---
references:
- kind: spec
  role: intent
  target: spec_extracted.txt
  title: Bookmark import and export specification
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkImporter.kt#preprocess
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/ClusterApprovalSheet.kt#ClusterApprovalSheet
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#commitImportBookmarks
---

# Import review

A browser bookmark file prepared for import, which the User reviews before anything is saved. It lasts until the User imports or cancels.

## Information kept

- **Links** — The proposed URLs and titles, source folders, and saved dates.
- **Suggested categories** — The category groups proposed by folder names and domain classification, with counts and sample domains.
- **Assigned categories** — The destination category chosen for each group.
- **Included links** — The groups and individual URLs currently selected for import.
- **Duplicate count** — The number of repeated addresses removed within the incoming file.
- **Format notice** — Whether the file lacks the standard browser bookmark header.
- **Progress** — The processed and total counts while importing.

## States

### Reviewing

The proposed links and category assignments await a decision.

### Importing

The selected links are being added to the stack.
