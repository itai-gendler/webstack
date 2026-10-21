---
id: webstack
summary: An Android visual bookmark manager for saving, organizing, finding, and moving a personal website stack.
category: productivity
tags:
- bookmarks
- android
- organization
authors:
- name: Chiranth Moger
license: MIT
languages:
- en
limitations:
- WebStack is an Android app; saved websites open in a browser app of the User's choosing.
- Each bookmark has exactly one tag at a time.
- There are no accounts. Bookmarks, tags and preferences are kept on the device and reach another device only through files the User exports and restores.
- A backup carries bookmarks and active tags, not previews or preferences.
- Browser bookmark import takes HTTP and HTTPS links only.
references:
- kind: doc
  role: intent
  target: README.md
- kind: spec
  role: intent
  target: spec_extracted.txt
  title: Bookmark import and export specification
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/example/data/BackupManager.kt#exportToJson
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/WebsiteSheets.kt
---

# WebStack

WebStack keeps a personal stack of websites on an Android device. The User saves links by typing them, from the clipboard, or by sharing them from another app; organizes them with tags, which can be reordered, parked off Home, renamed and deleted; finds them on Home by tag and search; and moves them in and out through browser bookmark files and WebStack backups.

## Intent

In the README's words: "Modern web navigation often leads to tab clutter and lost links buried deep within browser submenus. WebStack solves this by providing Android users with a centralized, visual bookmarking hub."
