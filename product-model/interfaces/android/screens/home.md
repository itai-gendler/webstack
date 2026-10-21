---
entities:
- entity: bookmark
  shows:
  - URL
  - Title
  - Domain
  - Category
  - Preview
  - Selected
- entity: tag
  shows:
  - Name
  - Position
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/cards/WebsiteCards.kt
---

# Home

The User's saved websites, narrowed to one tag (or All) and by search. Each bookmark shows its title, its domain and tag when Card Details turns them on, its preview when one is on the device, and its place in the selection while bookmarks are selected.
