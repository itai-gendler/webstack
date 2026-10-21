---
appliesTo:
- type: entity
  id: preferences
  effect: changes
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#setFallbackCategory
---

# The User changes the app preferences

The device's User chooses the app's preferences and acknowledges each release introduction.
