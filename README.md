# New Zealand Administrative Divisions / Aotearoa New Zealand



## Overview

| Item | Details |
|------|---------|
| Region | 17 |
| District | 68 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/nz](https://openadmindata.org/nz/) |
| API | [openadmindata.org/api/nz](https://openadmindata.org/api/nz/) |
| Flag | [PNG](https://onlygames.me/flags-png/nz/) · [SVG](https://onlygames.me/flags-svg/nz/) · [PDF](https://onlygames.me/flags-pdf/nz/) |
| National Anthem | [🎵 Listen & Download New Zealand National Anthem MP3](https://onlygames.me/national-anthems/nz/) |

## Browse by Region

| # | Region | Districts | Link |
|---|----|----|------|
| 1 | Northland | 3 | [Browse](divisions/northland-nz01/) |
| 2 | Nelson | 1 | [Browse](divisions/nelson-nz02/) |
| 3 | West Coast | 3 | [Browse](divisions/west-coast-nz03/) |
| 4 | Bay of Plenty | 7 | [Browse](divisions/bay-of-plenty-nz04/) |
| 5 | Canterbury | 10 | [Browse](divisions/canterbury-nz05/) |
| 6 | Marlborough | 1 | [Browse](divisions/marlborough-nz06/) |
| 7 | Hawke&#39;s Bay | 4 | [Browse](divisions/hawke-s-bay-nz07/) |
| 8 | Taranaki | 3 | [Browse](divisions/taranaki-nz08/) |
| 9 | Otago | 4 | [Browse](divisions/otago-nz09/) |
| 10 | Southland | 3 | [Browse](divisions/southland-nz10/) |
| 11 | Chatham Islands | 1 | [Browse](divisions/chatham-islands-nz11/) |
| 12 | Tasman | 1 | [Browse](divisions/tasman-nz12/) |
| 13 | Waikato | 10 | [Browse](divisions/waikato-nz13/) |
| 14 | Wellington | 8 | [Browse](divisions/wellington-nz14/) |
| 15 | Gisborne | 1 | [Browse](divisions/gisborne-nz15/) |
| 16 | Auckland | 1 | [Browse](divisions/auckland-nz16/) |
| 17 | Manawatu-Wanganui | 7 | [Browse](divisions/manawatu-wanganui-nz17/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 17 region records |
| [all-district.json](data/all-district.json) | JSON | All 68 district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=district |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
```

Districts are listed inline in each region's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
New Zealand Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/new-zealand-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
