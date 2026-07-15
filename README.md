# UC Bathroom Finder

An interactive, Google-Maps-style dashboard for finding gender-inclusive, single-occupancy, and public restrooms across all 9 University of California campuses.

**Live demo:** https://yanpeiw.github.io/UC-bathroom-finder/

## Overview

Each UC campus publishes some form of official restroom-location data (usually a gender-inclusive/all-gender restroom policy page, campus map API, or facilities PDF), but there was no single place to search across all of them on one map. This project compiles that data into one dashboard: pick a campus from the dropdown, search or filter by campus area, and click a pin to fly to it — the same interaction model as Google Maps.

## Features

- 444 real restroom locations across UC Berkeley, UC Davis, UC Irvine, UCLA, UC Merced, UC Riverside, UC San Diego, UC Santa Barbara, and UC Santa Cruz
- Interactive Leaflet.js map with OpenStreetMap tiles — pan, zoom, click pins
- Sidebar search + campus-area filter (e.g. Revelle, Science Hill, Health Sciences)
- Click any pin to open its popup, which includes an "Open in Google Maps" link that jumps straight to that exact coordinate for turn-by-turn directions
- Per-campus data-confidence badge, since source data quality varies by school
- Single self-contained HTML file — no build step, no server, no API keys required

## Data sources & methodology

Data was compiled from each campus's official public sources — gender-inclusive restroom policy pages, campus facilities offices, and (for UC San Diego) a public campus-map API. Where a campus publishes exact coordinates (UC Santa Cruz), those are used directly. Everywhere else, coordinates are approximate — placed at the building/area level rather than surveyed door locations, since most campuses don't publish per-restroom GPS data. Each campus panel notes its source and confidence level in the app itself.

This is a personal/portfolio project, not an official UC resource, and location accuracy should be verified in person if precision matters (e.g. accessibility needs).

## Tech stack

- HTML / CSS / vanilla JavaScript
- [Leaflet.js](https://leafletjs.com/) for the interactive map
- [OpenStreetMap](https://www.openstreetmap.org/) tiles
- Google Maps URL scheme (`maps.google.com/maps/search/?api=1&query=lat,lng`) for one-click directions — no API key needed

## Running locally

This is a single static HTML file with no dependencies to install. Clone the repo and open `index.html` directly in a browser, or serve it locally:

```bash
git clone https://github.com/yanpeiw/UC-bathroom-finder.git
cd UC-bathroom-finder
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

Hosted for free on GitHub Pages, served directly from `index.html` at the repo root (Settings → Pages → Deploy from branch `main`, folder `/root`). No separate hosting account or build step required.

## Roadmap / ideas

- Geocode exact coordinates for the remaining campuses (currently estimated)
- Add accessibility (ADA) and lactation-room layers
- Community-submitted corrections
- Extend beyond the UC system

## License

MIT — feel free to fork and adapt for your own school or district.
