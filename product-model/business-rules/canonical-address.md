---
appliesTo:
- type: entity
  id: bookmark
references:
- kind: spec
  role: intent
  target: spec_extracted.txt
  title: Bookmark import and export specification
- kind: code
  role: implementation
  target: app/src/main/java/com/example/bookmarks/BookmarkNormalizer.kt#dedupeKey
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/util/UrlUtils.kt#resolveDedupeKey
---

# Links that differ only in fragment, tracking parameters, www. or a trailing slash are the same link

Two links are the same when they match after removing the fragment, tracking parameters (utm_* plus fbclid, gclid, mc_eid and igshid), a leading www. and trailing slashes from the path, with the host lower-cased and a default port dropped. HTTP and HTTPS stay different links, and so do path case and the order of the remaining query parameters. The same comparison applies when saving, editing, importing and restoring. The bookmark keeps the address as given, trimmed, with https:// added when it has no scheme.
