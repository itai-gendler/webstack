---
appliesTo:
- type: entity
  id: tag
  effect: changes
  facts:
  - Position
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#updateCategoriesOrder
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#unparkCategory
---

# The User changes tag positions

The User orders the active tags and moves tags between the active and parked lists.
