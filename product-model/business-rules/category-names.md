---
appliesTo:
- type: capability
  id: add-tag
- type: capability
  id: rename-tag
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#addCategory
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#renameCategory
---

# Tag names are unique, ignoring case, across active and parked tags

Names are trimmed and compared ignoring case. A blank name, All, or a name another active or parked tag already has is refused; Personal is the built-in default tag.
