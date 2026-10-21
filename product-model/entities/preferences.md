---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#setFallbackCategory
singleton: true
---

# Preferences

The choices kept for this installation.

## Information kept

- **Theme** — The selected system, light, or dark theme preference.
- **Layout** — The chosen bookmark presentation mode.
- **Button shape** — The chosen add-button shape.
- **Show domain** — Whether saved website domains are shown on cards.
- **Show tags** — Whether saved website category labels are shown on cards.
- **Sort order** — Whether the newest or oldest saved bookmarks come first.
- **Fetch web previews** — Whether new website snapshots may be fetched; initially off.
- **Fallback tag** — The active tag that receives the bookmarks of a deleted tag; Personal at first.
- **Seen release** — The release introduction last acknowledged on this device.
