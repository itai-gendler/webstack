---
availability:
- place: android
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/sheets/WebsiteSheets.kt#AddWebsiteSheetContent
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/viewmodel/WebsiteViewModel.kt#saveWebsite
- kind: code
  role: implementation
  target: app/src/main/java/com/example/data/WebsiteRepository.kt#fetchAndSave
- kind: code
  role: implementation
  target: app/src/main/java/com/example/data/WebsiteRepository.kt#fetchTitleAsync
- kind: code
  role: implementation
  target: app/src/main/java/com/example/ui/util/UrlUtils.kt#extractUrlFromText
---

# Save bookmark

Save a website address under the chosen active tag. The capture form initially selects the first active tag, or Personal when none is available. The saved item does not wait for title retrieval.
