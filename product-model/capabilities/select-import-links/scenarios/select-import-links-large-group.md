---
kind: alternate
routes:
  android: Android
steps:
- text: Review a proposed group containing more than 40 links.
  kind: actor
  actor: user
  entities:
  - entity: import-review
    effect: reads
    facts:
    - Links
    - Included links
    - Suggested categories
  contexts:
    android:
      place: android::import
- text: Select the entire category group.
  kind: actor
  actor: user
  entities: []
  contexts:
    android:
      place: android::import
- text: Include every group link in the import review, including those represented by the remaining-link count.
  kind: product
  actor: user
  entities:
  - entity: import-review
    effect: changes
    facts:
    - Included links
  contexts:
    android:
      place: android::import
---

# Include a group larger than 40 links

## Trigger

A proposed group in Review Import has more than 40 links; only the first 40 are listed, followed by how many more there are.

## Outcome

Ticking the group includes every one of its links, listed or not; links can be left out one by one only among the first 40.
