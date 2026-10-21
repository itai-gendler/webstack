---
appliesTo:
- type: entity
  id: import-review
references:
- kind: spec
  role: intent
  target: spec_extracted.txt
  title: Bookmark import and export specification
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/DomainClassifier.kt#classifyAll
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/FolderCleaner.kt#canonicalDisplayNames
---

# Imported links take their browser folder first, then a known domain, then a shared domain

Each link takes the deepest folder in its browser path that is not a browser root or a generic name (such as Bookmarks bar, Other bookmarks, New folder or Misc), with numbering such as "01_" removed. A link with no such folder takes the category its domain has in the built-in domain list. Of the links still without one, three or more on the same registrable domain form a group named after that domain; the rest are Uncategorized. A folder name spelled several ways uses its most frequent spelling. These are proposals the User can change in the review.
