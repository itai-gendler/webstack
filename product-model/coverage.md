---
scope: Native Android bookmark workflows, category lifecycle, file transfer, preferences, and product-information
  surfaces.
method: Static inspection of tracked Kotlin, Android declarations, English product material, and selected test source.
covered:
- description: Native app entry, capture, saved-item actions, preferences, and core process surfaces.
  paths:
  - app/src/main/java/com/example/MainActivity.kt
  - app/src/main/AndroidManifest.xml
  - app/src/main/res/xml/shortcuts.xml
  - app/src/main/java/com/example/ui/
- description: Saved website persistence, duplicate comparison, metadata retrieval, and application backup handling.
  paths:
  - app/src/main/java/com/example/data/
- description: Browser file parsing, normalization, categorization, review preparation, confirmed insertion, and
    HTML export.
  paths:
  - app/src/main/java/com/example/bookmarks/
  - app/src/main/assets/
exclusions:
- description: Theme tokens, drawing primitives, icons, transitions, and static image assets; visual design rather
    than product contracts.
  paths:
  - app/src/main/java/com/example/ui/theme/
  - app/src/main/res/drawable/
  - docs/svg/
  - docs/screenshots/
  - fastlane/metadata/android/en-US/images/
- description: Build tooling, distribution recipes, release metadata, and automation; engineering and publication
    machinery.
  paths:
  - gradle/
  - app/build.gradle.kts
  - build.gradle.kts
  - settings.gradle.kts
  - .github/
  - metadata/
  - tools/
  - scripts/
- description: Test runners, benchmark harnesses, and fixture machinery; used as supporting evidence only.
  paths:
  - app/src/test/
  - app/src/androidTest/
  - testdata/
unmapped:
- description: Database upgrade code for earlier storage versions.
  paths:
  - app/src/main/java/com/example/data/WebsiteDatabase.kt
- description: Reset Defaults handling of custom tags in the tag view model and the Customize Tags sheet.
  paths:
  - app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt
  - app/src/main/java/com/example/ui/sheets/CustomizeTagsSheet.kt
- description: Last-backup date shown in Backup & Restore.
  paths:
  - app/src/main/java/com/example/ui/sheets/SettingsSheet.kt
- description: Share-sheet delivery helper for HTML exports.
  paths:
  - app/src/main/java/com/example/bookmarks/BookmarkDelivery.kt
limitations: []
---

# Coverage


