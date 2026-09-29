# Gunnison County Building Stock

An interactive, single-page data dashboard analyzing **18,312 building-level records**
from the Gunnison County (Colorado) Assessor's parcel database — what got built, when,
how big, and how it's graded.

**Live site:** https://eesterlein.github.io/gunnison-building-stock/

> **Independent research project.** This project is built from publicly available Gunnison County, Colorado assessor data downloads and GIS parcel data. It is not an official product of the Gunnison County Assessor's Office or Gunnison County, is not a system of record, and may contain errors or out-of-date information. Always verify against official county records.

## What's in it

| # | Section | Shows |
|---|---------|-------|
| 01 | Construction era | Buildings by decade built (Pre-1900 → 2020s), including 2,134 with no recorded year |
| 02 | Property mix | Share of building *count* vs. share of *floor area*, by property class |
| 03 | Building size | Average above-grade square footage by decade of construction |
| 04 | Assessor grades | Construction-quality (13 grades) and condition distributions |
| 05 | Residential rooms | Bedroom and bathroom counts for 10,997 residential buildings |
| 06 | Use & occupancy | Top 12 assessor occupancy tags (of 385 distinct) |
| 07 | Summary | Every property class side by side — count, footprint, average rooms, year |

Charts are hand-drawn SVG with hover tooltips. The page is theme-aware (light/dark) and responsive.

## Tech

Plain HTML + CSS + vanilla JavaScript in a single `index.html` — no build step, no
dependencies. Web fonts (Public Sans, IBM Plex Mono) load from Google Fonts; everything
else is inline. All figures are baked into the script as static data arrays.

## Running locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Data source

Gunnison County Assessor building-attribute records, file *"Building Attributes 8.3.26"*
(n = 18,312). Decade-built figures use original year of construction. Bedroom, bathroom,
and average-year figures for the Residential class exclude records with no value recorded.
Occupancy tags are assigned by the assessor and are not mutually exclusive with property
type. Percentages are rounded and may not sum to exactly 100%.
