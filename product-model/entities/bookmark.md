---
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/data/Website.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/cards/WebsiteCards.kt#WebsiteSnapshotImage
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#WebStackScreen
---

# Bookmark

A saved website: what the User finds on Home, opens, shares, edits and deletes.

## Information kept

- **URL** — The saved address, including its meaningful query and original fragment.
- **Title** — The website title, supplied by import or editing, or fetched after capture.
- **Domain** — The host derived from the address.
- **Category** — The one tag this bookmark is filed under.
- **Saved at** — The saved date used for sorting and file transfer.
- **Source folders** — The original browser folder path retained for HTML imports when present.
- **Preview** — The snapshot of the website kept on the device, once one has been fetched.
- **Selected** — Whether the bookmark is in the current selection for bulk deletion, and its position in it.
