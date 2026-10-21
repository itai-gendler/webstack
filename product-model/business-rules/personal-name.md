---
appliesTo:
- type: entity
  id: tag
  effect: changes
  facts:
  - Name
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#renameCategory
permits:
- actors:
  - user
  when:
  - fact: Name
    is-not: Personal
---

# The User may rename any tag except Personal

Personal is the default tag and keeps its name; no other tag can be renamed to Personal either.
