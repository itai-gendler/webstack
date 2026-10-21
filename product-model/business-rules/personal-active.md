---
appliesTo:
- type: entity
  id: tag
  effect: changes
  to: Parked
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#parkCategory
permits:
- actors:
  - user
  when:
  - fact: Name
    is-not: Personal
---

# The User may park any tag except Personal

Personal is the default tag and always stays on Home; the app says it cannot be hidden.
