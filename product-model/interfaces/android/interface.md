---
type: mobile-app
actors:
- user
languages:
- en
references:
- kind: code
  role: implementation
  target: app/src/main/AndroidManifest.xml
- kind: code
  role: implementation
  target: app/src/main/java/com/example/MainActivity.kt#handleIncomingIntent
- kind: code
  role: implementation
  target: app/src/main/res/xml/shortcuts.xml
---

# Android app

The user works with their device’s saved bookmarks through the native Android app. Android text sharing opens a prefilled capture form; launcher shortcuts open capture or search. Opening a WebStack backup file invokes restoration. File pickers, browsers, and sharing applications provide the external hand-offs.
