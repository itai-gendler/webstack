---
kind: primary
routes:
  android: Android
steps:
- text: Deselect one link, exclude a category group, or choose Deselect All.
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
- text: Remove the requested links from the import review selection. With no links included, Import is unavailable.
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

# Leave links out of an import

## Trigger

In Review Import, the User unticks one link, unticks a whole group, or chooses Deselect All.

## Outcome

Those links are left out of the import and the Import button shows the new count; with nothing included, Import is unavailable.
