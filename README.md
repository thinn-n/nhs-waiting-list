# NHS Waiting List Atlas

An interactive, NHS-branded dashboard mapping England's hospital waiting lists region by region, built from official NHS England data.

**Live site:** https://ollielie.github.io/nhs-waiting-atlas/

![NHS Waiting List Atlas: a light, medical-themed interactive map and dashboard](preview.png)

## What it shows

Consultant-led Referral to Treatment (RTT) waiting-list figures for each of the seven NHS England commissioning regions, as of July 2026.

- **14.0M** patient pathways waiting to start treatment
- **65.3%** seen within 18 weeks — against a **92%** constitutional target
- **212,806** patients waiting more than a year (52+ weeks)
- No English region meets the target; the best manages just **68.8%**

The headline finding: **East of England is furthest from the target at 61%** and carries the most year-plus waits, while **the Midlands holds the largest list overall** at 2.66 million pathways.

## Understanding the data

"RTT" is the clock that measures how long a patient waits from GP referral to the start of hospital treatment. Figures are **pathways, not individual patients** — one person can be on more than one pathway at once. The 92% within-18-weeks standard is a long-standing NHS constitutional target that has not been met nationally in recent years.

## Features

An interactive dashboard where the map and charts are linked, in the style of a BI tool:

- **Linked highlighting** — hover a chart bar and its region lights up on the map (and vice versa)
- **Power BI–style hover cards** — a floating panel shows each region's full breakdown (patients waiting, % within 18 weeks, 52/65/78-week waits) colour-coded by performance
- **Click to drill in** — click any bar to fly the map to that region and open its detail
- **Triage colour coding** — green (closest to target) through amber to red (furthest), following clinical triage logic
- **Live-data motion** — region markers gently "breathe", the worst-performing region pulses as an alert, and an animated ECG line runs through the header
- **Recolour and jump-to controls**, animated count-up statistics, keyboard accessibility and reduced-motion support

## Design

Themed around the NHS's own visual identity: the official NHS blue (`#005EB8`), a clean clinical light layout, white cards, and the NHS logo lockup — so it reads like it belongs on nhs.uk.

## Data

Source: [NHS England — Consultant-led Referral to Treatment (RTT) Waiting Times](https://www.england.nhs.uk/statistics/statistical-work-areas/rtt-waiting-times/), the "Incomplete Commissioner" file for July 2026.

The raw file is a ~4 MB spreadsheet with over 100 columns and one row per region × treatment function. It was cleaned and aggregated to regional totals, and the within-18-weeks percentage recalculated from the underlying counts.

## Built with

- [Leaflet](https://leafletjs.com/) for the map
- Esri light-grey tiles for the basemap
- Plain HTML, CSS and JavaScript — no build step, no dependencies
- A single self-contained file that opens in any browser and works offline

## Running locally

No build tools required. Clone the repo and open `index.html` in a browser:

```bash
git clone https://github.com/ollielie/nhs-waiting-atlas.git
cd nhs-waiting-atlas
open index.html
```

## Licence & attribution

Waiting-list data is published by NHS England under the Open Government Licence. This project is a personal data-visualisation piece and is not affiliated with or endorsed by NHS England. "NHS" and the NHS logo are trademarks of the UK Department of Health and Social Care, used here only to present NHS data faithfully.
