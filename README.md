# Denver Metro Crash Hotspot Dashboard

Interactive map and data dashboard covering traffic crashes across the Denver metro area. Built with public data so people can actually see where crashes are concentrated and how bad specific intersections really are.

## What's in it

- Interactive Leaflet map with the 20 worst crash intersections pinned to their exact locations
- Filter by crash type (pedestrian, cyclist, fatal)
- Year over year comparison (2022, 2023, 2024)
- Address search to find crash hotspots near any location
- Commute mode that routes between two points and flags danger zones along the way
- Six major corridor overlays (Federal, Colfax, I-25, Colorado Blvd, I-70, Alameda)
- Charts covering crash timing, contributing factors, neighborhood breakdowns, and metro comparisons

## Data sources

All data comes from publicly available sources:

- [Denver Open Data Catalog](https://opendata-geospatialdenver.hub.arcgis.com/) for crash records
- [CDOT Crash Data](https://www.codot.gov/safety/traffic-safety/data-analysis/crash-data) for statewide numbers
- [Denver Vision Zero](https://denvergov.org/Government/Citywide-Programs-and-Initiatives/Vision-Zero/Statistics) for fatality and serious injury tracking
- [TomTom Traffic Index](https://www.tomtom.com/traffic-index/) and [INRIX](https://inrix.com/scorecard/) for congestion data

## Privacy

This page has no backend, no analytics, and no cookies. Nothing you type is stored or collected. Address search uses [OpenStreetMap Nominatim](https://nominatim.openstreetmap.org/) and commute routing uses [OSRM](https://project-osrm.org/), both open source. Your queries go directly to those services and never pass through anything I control.

## Running it

It's a single HTML file. Open `index.html` in a browser or host it anywhere that serves static files.

## Some numbers that stood out

- I-70 at Peoria: 103 crashes in 2024 (roughly one every 3.5 days)
- Alameda & Federal and I-25 SB at Yale: 3 fatal crashes each in 2024
- 62 people died on Denver roads in 2024
- 590 crashes involved pedestrians
- Denver's Vision Zero goal is zero deaths by 2030. In 2025 the city recorded 93 fatalities.

No affiliation with any law firm, insurance company, or government agency.
