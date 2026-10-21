---
appliesTo:
- type: entity
  id: bookmark
  effect: changes
  facts:
  - Preview
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/cards/WebsiteCards.kt#WebsiteSnapshotImage
permits:
- actors:
  - user
  when:
  - entity: preferences
    fact: Fetch web previews
    is: true
---

# New previews are fetched only while Fetch Web Previews is on

Fetching a new or refreshed preview needs Fetch Web Previews on. Previews already on the device stay visible when it is off.
