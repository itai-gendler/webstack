---
appliesTo:
- type: entity
  id: tag
  effect: removes
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#deleteCategory
permits:
- actors:
  - user
  when:
  - fact: Name
    is-not: Personal
---

# The User may delete any tag except Personal

Personal is the default tag; the app says it cannot be deleted.
