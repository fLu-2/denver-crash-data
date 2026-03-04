# Denver Metro Crash Hotspot Dashboard

Interactive map and data dashboard covering traffic crashes across the Denver metro area. Built with public data so people can actually see where crashes are concentrated and how bad specific intersections really are.

## What's in it

Interactive Leaflet map with the 20 worst crash intersections pinned to their exact locations (coordinates verified manually via Google Maps). Filter by crash type (pedestrian, cyclist, fatal), compare across years (2022, 2023, 2024), or toggle between total crash count and crashes per million vehicles per year using CDOT traffic volume data. Rankings completely reshuffle when you normalize by volume.

Address search to find crash hotspots near any location. Commute mode that routes between two points and flags danger zones along the way. Six major corridor overlays (Federal, Colfax, I-25, Colorado Blvd, I-70, Alameda).

Vision Zero accountability section tracking Denver's fatality count from the 2017 baseline (51 deaths) through 2024 (62 deaths) against the city's stated goal of zero by 2030. Includes a pedestrian fatality trend showing those numbers still climbing year over year.

Charts covering crash timing (hourly weekday vs weekend, day of week with the Tuesday spike), year over year severity trends, neighborhood breakdowns, vulnerable road user crashes, pedestrian crash locations (intersection vs midblock), and metro area comparisons.

Sticky navigation bar that pins to the top of the screen once you scroll past the hero section. Highlights the active section as you scroll and lets you jump between all 10 sections. Horizontally scrollable on mobile.

## Sections

01 Crash Map (interactive, filterable, searchable, commute routing)
02 Dangerous Intersections (top 10 table, total and per vehicle ranking)
03 By Neighborhood (crash counts by area)
04 When It Happens (hourly, day of week, monthly patterns)
05 Year Over Year (fatality and severity trends 2019 to 2024)
06 Vision Zero Accountability (promise vs reality chart, pedestrian fatalities)
07 Pedestrians & Cyclists (VRU crashes, crash location breakdown)
08 The Metro Picture (Denver vs Aurora, Colorado Springs, and surrounding counties)
09 Key Takeaways
10 Methodology & Sources

## Data sources

All data comes from publicly available sources:

Denver Open Data Catalog for crash level records. CDOT Crash Data for statewide numbers. CDOT Traffic Data Explorer for AADT (Annual Average Daily Traffic) used in crash rate normalization. Denver Vision Zero for fatality and serious injury tracking. TomTom Traffic Index and INRIX for congestion data. Denver Police Department fatality counts as reported by Westword, Denver Streets Partnership, and CDOT for the Vision Zero accountability charts. Denver DOTI for pedestrian fatality counts.

## Methodology notes

Traffic volume normalization uses AADT from CDOT's Traffic Data Explorer and ArcGIS Traffic Volume Map. At intersections the higher volume approaching road was used. AADT reflects the most recent published year.

Crash data only includes crashes with a filed police report. Pedestrian and cyclist incidents are widely understood to be underreported. If no report is filed the crash does not appear in Denver Open Data. The real numbers are likely higher than what is shown.

At interstate locations (I-25, I-70, I-76), crash counts include all crashes near the interchange including on ramps, bridges, overpasses, and adjacent roads. The source data groups crashes by proximity and does not distinguish mainline vs ramp vs crossing road.

The Vision Zero accountability chart uses DPD fatality counts which may differ slightly from CDOT statewide methodology. The goal trajectory assumes linear reduction from the 2017 baseline (51) to zero in 2030.

## Privacy

This page has no backend, no analytics, and no cookies. Nothing you type is stored or collected. Address search uses OpenStreetMap Nominatim and commute routing uses OSRM, both open source. Your queries go directly to those services and never pass through anything I control.

## Running it

It's a single HTML file. Open index.html in a browser or host it anywhere that serves static files.

## Some numbers that stood out

I-70 at Peoria: 103 crashes in 2024, roughly one every 3.5 days. Alameda & Federal: highest crash rate per vehicle in Denver at 5.2 crashes per million vehicles per year. Alameda & Federal and I-25 SB at Yale: 3 fatal crashes each in 2024. 62 people died on Denver roads in 2024. 590 crashes involved pedestrians. Pedestrian fatalities climbed from 23 in 2021 to 26 in 2024. Denver's Vision Zero goal is zero deaths by 2030. Fatalities have increased 21% since the program launched in 2017. In 2025 the city recorded 93 fatalities, the worst since 2013.

No affiliation with any law firm, insurance company, or government agency.
