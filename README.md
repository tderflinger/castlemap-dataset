# Castles of the World — 7,044 castles, fortresses & palaces

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21322359.svg)](https://doi.org/10.5281/zenodo.21322359)

A curated, hand-checked dataset of the world's **7,044 great castles, fortresses, palaces and ruins across 141 countries** — every landmark verified to have exact coordinates, a real Wikimedia Commons photo and an English Wikipedia article.

This is the exact dataset behind **[Castlemap](https://thecastlemap.com)**, a free interactive night-map of all 7,044 landmarks.

- 🗺️ Interactive map: https://thecastlemap.com
- 📄 Dataset page & downloads: https://thecastlemap.com/data/
- 🏆 Fame ranking (methodology): https://thecastlemap.com/castles/ranked/
- 🤖 Live MCP server for AI agents: `https://thecastlemap.com/mcp` (Model Context Protocol, streamable HTTP, no key — tools: `search_castles`, `get_castle`, `castles_near`, `top_castles`, `list_countries`, `random_castle`)

## Files

| File | Format | Contents |
|---|---|---|
| `castles.geojson` | GeoJSON FeatureCollection | 7,044 Point features with all properties |
| `castles.csv` | CSV (UTF-8, header row) | Same records, flat |

## Fields

| Field | Description |
|---|---|
| `qid` | Wikidata item ID (e.g. `Q2946`) — join key to the whole linked-data web |
| `name` | English name |
| `category` | `castle` \| `fortress` \| `palace` \| `ruin` |
| `country`, `iso` | Country name and ISO 3166-1 alpha-2 code |
| `lat`, `lon` | WGS84 coordinates (verified) |
| `year`, `century` | Founding year and century, where documented (5,302 of 7,044 carry a year) |
| `year_approx` | Whether that year is an approximation rather than a documented date — `1`/`0` in the CSV, `true`/`false` in the GeoJSON. True for 1,378 records |
| `wikipedia` | English Wikipedia article URL |
| `image` | Wikimedia Commons photo URL |
| `image_by` | Photographer, as credited on Commons — most of these licences require you to name them if you reuse the picture |
| `image_licence` | The photo's licence (e.g. `CC BY-SA 4.0`, `Public domain`). Applies to the photograph only, never to this dataset |
| `sitelinks` | Number of Wikipedia language editions covering the landmark |
| `pageviews` | Wikipedia pageviews over the trailing 60 days, summed across every language edition that covers the landmark |
| `fame_rank` | Global fame rank 1…7044 — a blend of Wikipedia language coverage (`sitelinks`) and readership (`pageviews`). Rank 1 = Palace of Versailles. [Methodology](https://thecastlemap.com/castles/ranked/) |
| `url` | The landmark's page on thecastlemap.com |

`image_by` and `image_licence` were added on 2026-08-08 and are present for 7,029 of the 7,044 records. CSV columns are appended, never reordered: the column order is a contract with everyone who has already cited the file.

## Provenance & method

Curated from **[Wikidata](https://www.wikidata.org)** (CC0). Candidates are filtered to significant, well-documented sites: exact coordinates required, a real Commons photo required, an English Wikipedia article required; categories normalized; countries normalized; duplicates and phantom entries removed by hand. The dataset refreshes from Wikidata — spot an error or a missing castle? Improve its Wikidata entry and it flows into the next release.

## Mirrors & citation

- GitHub: https://github.com/Flightmussy/castlemap-dataset
- Hugging Face: https://huggingface.co/datasets/Flightmussy/castles-of-the-world
- Kaggle: https://www.kaggle.com/datasets/flightmussy/castles-of-the-world
- **Citable DOI (Zenodo): [10.5281/zenodo.21322359](https://doi.org/10.5281/zenodo.21322359)**

## Releases

- **v2.0.0** (2026-08-17) — **2,435 → 7,044 landmarks, 129 → 141 countries**, the largest expansion the dataset has had. It closes the gap that the previous release opened up between this file and the live atlas: the map had grown for a month while the published dataset stood still, so anyone downloading it was getting a third of the atlas. Thin countries were raised toward a per-country floor (Spain 500, Germany 475, France 456, Italy 416, Poland 360, England 315, Japan 296), whole classes that had been unreachable were admitted — the fortification superclass is now resolved globally rather than per country, which alone recovered 56 well-known fortifications — and Andean, Australian and Gulf sites were added from reader reports. Category counts: 3,180 castles · 1,453 fortresses · 1,024 palaces · 1,387 ruins. Four new fields: `year_approx`, `image_by`, `image_licence` and `url`; the CSV also carries `url`, which previously only the GeoJSON did, so a row can now be linked back to its page. Founding years were re-audited against each landmark's Wikipedia lead in eleven further languages.

- **v1.2.0** (2026-07-19) — 27 corrections. 26 founding years that were really renovation or heritage-designation dates in Wikidata (the Tang-dynasty Daming Palace claimed 2010 → now 634; Chapultepec 1944 → 1785; Sanok 2010 → 1523; a cluster of Czech castles stamped with their 2000 national-monument decree…) were fixed to the documented construction start, and Erebuni Fortress moved from the defunct historical state "Urartu" to Armenia — the dataset now spans 129 countries. These years power the new oldest-castles ranking: https://thecastlemap.com/castles/oldest/

- **v1.1.0** (2026-07-19) — 2,400 → 2,435 landmarks (4 Norwegian fortresses and 9 Indian landmarks added on reader request, plus 22 further ruins; the phantom "French Third Republic" country is gone — the Imperial City of Huế now sits under Vietnam, so 130 countries). 225 category corrections: an unambiguous display name now beats Wikidata's often-sloppy P31 typing (83 fixes — Kufstein Fortress is no longer a "castle"), and *ruin* is now a state that wins over the building type, read from each monument's English Wikipedia lead (142 fixes — Heidelberg, Poenari, Tantallon, the Slovak hilltop castles). Category counts: 1,031 castles · 427 fortresses · 716 palaces · 261 ruins.
- **v1.0.0** (2026-07-12) — first release: 2,400 landmarks across 131 countries.

## License

**Facts/data: [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)** — public domain dedication; use for anything, no permission needed. Attribution to [Castlemap](https://thecastlemap.com) is appreciated but not required.

Photos and Wikipedia texts referenced by URL are **not** part of this dataset and remain under their own licenses (see each Commons/Wikipedia page).
