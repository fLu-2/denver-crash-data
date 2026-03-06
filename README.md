# Denver Metro Traffic Crash Dashboard

Interactive map and data dashboard covering traffic crashes across the Denver metro area — Denver, Aurora, Lakewood, Arvada, Westminster, and Thornton. Built with public data from CDOT statewide crash listings so people can actually see where crashes are concentrated, how bad specific intersections really are, and how their city compares.

## What's in it

**Interactive crash map** with 65 intersections pinned across 6 metro regions (coordinates verified manually via Google Maps). Filter by crash type (pedestrian, cyclist, fatal), compare across years (2022–2024), toggle between total crash count and crashes per million vehicles using CDOT AADT data. Rankings completely reshuffle when you normalize by volume. Each chart has its own independent metro dropdown so you can compare Aurora's crash types alongside Denver's hourly pattern and Lakewood's day-of-week distribution simultaneously.

**Address search** to find crash hotspots near any location. **Commute mode** that routes between two points and flags danger zones along the way. **12 corridor overlays** spanning the full metro: I-25 (south Denver to 120th Ave), Colfax (Kipling to Tower Rd), Wadsworth (Lakewood through Arvada to Westminster), I-70, I-225, Havana St, Federal Blvd, Colorado Blvd, Alameda Ave, Parker Rd, Chambers Rd, and Sheridan Blvd.

**Impaired driving breakdown** from CDOT's alcohol, marijuana, and other drugs suspected fields. Shows impairment rate by hour of day (over 20% of crashes between midnight and 3am involve impairment), substance breakdown (alcohol dominates at 88% of impaired crashes), and each city's share of impaired fatalities.

**Speed analysis** using CDOT contributing factors and estimated speed vs. posted limit data. Speed accounts for just 5% of crashes but 30% of fatalities. Aurora stands out at 42% of its traffic deaths involving speed. Includes speed crashes by posted speed limit zone, showing that 25–35 mph residential streets produce the most speed crashes in Denver while 40 mph arterials dominate in Aurora.

**Vision Zero accountability** tracking Denver's fatality count from the 2017 baseline (51 deaths) through 2024 (62 deaths) against the city's stated goal of zero by 2030. Fatalities have increased 21% since the program launched. In 2025, the city recorded 93 fatalities, the worst since 2013.

**18 independently filterable charts**, each with its own metro dropdown defaulting to "All Metro." Crash types, contributing factors, hourly patterns, day of week, monthly totals, intersection vs. mid-block split, YoY total crashes, YoY fatalities and pedestrian crashes, fatality bars, vulnerable road user trends, impairment rate by hour, substance breakdown, impaired fatalities by city, speed rate by hour, speed crashes by zone, speed fatalities by city, per-capita metro comparison, and the statewide trend.

Sticky navigation bar with 11 sections. Horizontally scrollable on mobile with 3 responsive breakpoints.

## Sections

01. **Crash Map** — interactive, filterable, searchable, commute routing, 65 intersections, 12 corridors
02. **Dangerous Intersections** — top 10 table with total and per-vehicle ranking, corridor table
03. **The Calendar of Risk** — monthly, day of week, hourly patterns (all metro-filterable)
04. **Year Over Year** — total crashes, fatalities, pedestrian and severity trends 2022–2024
05. **Impaired Driving** — impairment rate by hour, substance breakdown, impaired fatality share
06. **Speed** — speed crash rate by hour, crashes by speed limit zone, speed's share of fatalities
07. **Vision Zero Accountability** — promise vs. reality chart, fatality trend, +21% callout
08. **Pedestrians & Cyclists** — VRU crash trends, crash location breakdown (intersection vs. mid-block)
09. **The Metro Picture** — per-capita crash rates, statewide trend
10. **Sources** — Denver Open Data, CDOT, Vision Zero, TomTom/INRIX with links
11. **Methodology** — data sourcing, normalization, underreporting, interchange methodology, VZ data notes

## Data sources

All data comes from publicly available sources. The primary dataset is the CDOT Statewide Crash Data Listing, processed for 2022 (95,383 records), 2023 (102,764 records), and 2024 (101,320 records). Every single-year chart uses 2024 as the baseline. Every trend chart uses 2022–2024.

- **CDOT Statewide Crash Listings** — crash type, contributing factors, severity, alcohol/marijuana/drugs suspected, speed limit, estimated speed, time, location, city, county. Processed all ~300K records across three years.
- **CDOT Highways in Colorado** — 81,600 road segments with AADT, matched to intersections by coordinate proximity for per-vehicle crash rate normalization.
- **Denver Open Data Catalog** — crash-level records from Denver PD.
- **Denver Vision Zero / DOTI** — fatality and serious injury tracking, pedestrian fatality counts.
- **TomTom Traffic Index / INRIX** — rush-hour speeds and congestion data.
- **DPD fatality counts** as reported by Westword, Denver Streets Partnership, and CDOT for the Vision Zero accountability chart.
- **2024 ACS population estimates** for per-capita crash rate calculations.

## Methodology notes

**Standardized on 2024.** All single-year snapshot charts (crash types, contributing factors, hourly, DOW, monthly, ped location, impairment, speed) use the 2024 CDOT statewide crash listing. All trend charts use 2022–2024. The 2025 partial-year file (82,716 records, Jan–Nov 25) is used only for map intersection coordinate matching.

**Metro city mapping.** Each crash record is assigned to a metro city based on the CDOT City field: Denver, Aurora, Lakewood, Arvada, Westminster/Thornton (includes Northglenn). The "Unincorporated" bucket (Adams, Arapahoe, Jefferson, Boulder, Broomfield, Douglas counties) is available as a map/chart filter but excluded from the per-capita comparison chart since it's a catch-all for every other municipality and unincorporated area.

**Traffic volume normalization** uses AADT from CDOT's Highways in Colorado dataset (data.colorado.gov, 81,600 road segments) matched to intersections by coordinate proximity. At intersections, the higher-volume approaching road was used. Six city-street intersections without CDOT highway coverage use estimates.

**Impaired driving** is flagged when any of the CDOT alcohol/marijuana/other drugs suspected fields indicate "Yes" (via breath test, SFST, observation, or other method) for either traffic unit. Marijuana is flagged when the field reads "Marijuana Suspected" (excluding "Marijuana Not Suspected" and "Unknown").

**Speed-related crashes** are identified by contributing factor ("Too Fast for Conditions," "Exceeded Authorized Speed," "Racing") or when estimated/actual speed exceeds the posted limit by more than 10 mph.

**Crash data only includes crashes with a filed police report.** Pedestrian and cyclist incidents are widely understood to be underreported. The real numbers are likely higher.

**Highway interchanges.** At interstate locations (I-25, I-70, I-76, I-225), crash counts include all crashes near the interchange — on ramps, bridges, overpasses, and adjacent roads. The source data groups crashes by proximity.

**Vision Zero data** uses DPD fatality counts which differ from CDOT methodology for some years (notably 2022: DPD reports 84, CDOT reports 72). The goal trajectory assumes linear reduction from the 2017 baseline to zero in 2030.

**Contributing factors** are reported as a percentage of total factor entries, since each crash can generate multiple factor records (up to 4 columns checked per record). Denver averaged 1.47 factor entries per crash in 2024.

## Privacy

This page has no backend, no analytics, and no cookies. Nothing you type is stored or collected. Address search uses OpenStreetMap Nominatim and commute routing uses OSRM, both open source. Your queries go directly to those services and never pass through anything I control.

## Running it

Single HTML file. Open index.html in a browser or host it anywhere that serves static files. Map tiles load from CARTO's CDN. Charts use Chart.js. Map uses Leaflet.

## Some numbers that stood out

- **56,697** crashes across the Denver metro in 2024 (CDOT).
- **293** traffic fatalities metro-wide in 2024.
- **I-70 at Peoria:** 103 crashes in 2024, roughly one every 3.5 days.
- **I-225 interchanges in Aurora** are the biggest crash generators in the metro outside I-25 (120–135 crashes each).
- **104th & I-25 in Thornton:** highest crash count in north metro at 164.
- **Denver:** 21.5 crashes per 1,000 residents. Arvada: 12.8.
- **Aurora:** 42% of its traffic fatalities involved speeding. Nearly half of Colorado's 50 most dangerous intersections are in Aurora (Ridder Law / CDOT).
- **28%** of all metro fatalities involved impairment. Between midnight and 3am, over 20% of all crashes involve a suspected impaired driver.
- **1,248** pedestrian crashes and **810** cyclist crashes across the metro in 2024.
- **Denver's Vision Zero:** fatalities increased 21% since the program launched in 2017 (51 → 62 deaths). In 2025, the city recorded 93 fatalities, the worst since 2013.
- **Careless driving** is the #1 contributing factor at 16% of reported factors in Denver. Broadened to include all distracted/careless subcategories, it reaches 37%.

No affiliation with any law firm, insurance company, or government agency.
