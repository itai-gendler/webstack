---
kind: primary
routes:
  android: Android
steps:
- text: Select a previously excluded link, include its category group, or choose Select All.
  kind: actor
  entities:
  - entity: import-review
    effect: reads
    facts:
    - Links
    - Included links
  actor: user
  contexts:
    android:
      place: android::import
- text: Add the requested links to the import review selection. Including a group clears individual exclusions within
    it; Select All clears all exclusions.
  kind: product
  entities:
  - entity: import-review
    effect: changes
    facts:
    - Included links
  actor: user
  contexts:
    android:
      place: android::import
---

# Put links back into an import

## Trigger

In Review Import, the User ticks a link left out earlier, ticks a whole group, or chooses Select All.

## Outcome

Those links are included again and the Import button shows the new count. Ticking a group includes all its links; Select All includes every link.
