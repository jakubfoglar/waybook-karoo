# Waybook — Notices & Attribution

Waybook itself is proprietary software, free to use under the [Waybook License](./LICENSE)
— it is **not** open source, and all rights are reserved. This file records the
third-party data, content and software Waybook builds on, and the terms under which they
are used. These upstream obligations are independent of Waybook's own license and continue
to apply to Waybook and to the catalogs it produces.

## Trademarks

Waybook is an independent, third-party extension. It is **not affiliated with,
endorsed by, or sponsored by Hammerhead or SRAM**. "Hammerhead" and "Karoo" are
trademarks of their respective owners and are used here only to describe
compatibility.

## Data sources

Every place card Waybook builds is assembled from open data. Each place carries a
small-print footer naming the specific sources used for it; the categories are:

### Place locations & practical tags — OpenStreetMap

Place geometry, names, categories, opening hours, admission, phone and website tags
come from **OpenStreetMap**, queried live via the Overpass API.

- © OpenStreetMap contributors
- Licensed under the **Open Database License (ODbL) v1.0** — https://opendatacommons.org/licenses/odbl/1-0/
- OSM copyright and licence — https://www.openstreetmap.org/copyright

### Descriptive text — Wikipedia & Wikivoyage

Short place descriptions and the facts the guide paragraphs are written from come
from **Wikipedia** and **Wikivoyage** (via their REST/API summary and extract
endpoints), with entities resolved through **Wikidata**.

- Text © the respective Wikipedia / Wikivoyage contributors
- Licensed under **Creative Commons Attribution-ShareAlike (CC BY-SA)** —
  https://creativecommons.org/licenses/by-sa/4.0/
- Wikidata statements are published under **CC0**.

### Photos — Wikimedia Commons

Place photos come from **Wikimedia Commons**. Licences vary **per image**; Waybook
shows the author and licence short-name for each photo it displays (from the Commons
`extmetadata`), on the place's detail screen.

- Each image © its respective author, under its own licence (CC BY-SA, CC BY, CC0,
  public domain, etc.) as shown on the card.
- Wikimedia Commons — https://commons.wikimedia.org

### Venue self-descriptions — the venues' own websites

For places carrying an OSM `website` tag, Waybook may fetch that page (honouring
`robots.txt`) to read practical facts (opening hours, cuisine, phone) and a short
self-description. Such text is always shown **quoted and attributed to the venue**
("From their website: …"), never folded into Waybook's editorial voice, and always
date-stamped.

## Generated text

Some guide paragraphs are written by a large language model **from the retrieved
Wikipedia/Wikivoyage facts only** — never from the model's own memory — and cached.
Where no reliable source exists, the place stays a plain factual row rather than
carrying an invented story. See [docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md) for
the confidence-tier design that enforces this.

## Bundled software

- **karoo-ext** (`com.github.hammerheadnav:karoo-ext`) — the Hammerhead Karoo
  extension SDK, consumed via JitPack.
- Kotlin, kotlinx-coroutines, kotlinx-serialization, AndroidX, and Timber — under
  their respective open-source licences (Apache-2.0 / MIT), retrieved at build time.
- The committed `app/debug.keystore` is an Android debug keystore with the standard
  public password (`android`). It exists only so every CI build is signed identically
  and in-app updates install over one another. It is **not** a production signing key
  and grants no privilege.
