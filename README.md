# 2026 World Cup Transportation Dashboard

**Live site:** https://tngjcall.github.io/nyc-worldcup-transportation-dashboard-pages/

An interactive map of how transportation in US host cities behaves around the
2026 FIFA World Cup: subway, bus, bike share, taxi and ride-hail, road speeds,
tolls and parking, hour by hour, with the match schedule on the same timeline.
Built for an academic study of the tournament's transportation impact. New York
City is covered in depth; Seattle, Los Angeles, the San Francisco Bay Area and
Boston have the layers their open data allows.

---

## How to use

### Map View

**Choose a city and data**
- Pick a city at the top (New York City, Seattle, Boston, Los Angeles, Bay Area).
- In **Data Layer** on the left, pick one or more layers. Each layer becomes a chip under the menu: drag chips to reorder; click a chip to open its data source.
- Area layers (census tract, NTA, CDTA, taxi zone, borough) have a level switch next to the chips.
- Some layers have extra switches in a bar above the map: Zone Function (*Colour by*, viewing sites), Bus Network (routes / stops), POI (bars, pubs, nightclubs, restaurants, hotels, Airbnb).

**Move through time**
- The time player at the bottom of the map: **Hours** steps hour by hour (10 / 15 / 30 min where the source has it), **Days** shows daily totals, **Matches** shows a window around each kickoff (pick matches, then step from before kickoff to after).
- Pick a date in the calendar or a time in the clock menu; press play to animate; change speed with 0.5× – 4×.

**Read the map**
- The legend shows the colour scale. **Max from** sets where the top of the scale comes from: this hour, the day, week, month (default), year or all data.
- Several legends stack in one box; click a legend's title to expand it. Drag the legend or the map buttons (home / zoom / satellite / heatmap) to any corner; drag the legend's edge to resize it.
- Right-click the map for more: hide zero / missing values, hide unselected features, show a route's stops, jump to a related layer.

**Select and inspect**
- Click a feature to see its values in **Feature Info**. Ctrl / Cmd-click to add more; Ctrl / Cmd-drag to box-select.
- With nothing selected, Feature Info lists every feature of the top layer; sort it high → low or low → high, and search in the active layers.
- The **?** next to the play button explains how a layer is calculated (Zone Function, parking occupancy).
- The download button (top-left of the map) saves what is on screen as CSV, JSON or JPG.

### Line Chart

1. Switch to **Line Chart** (top-left) and pick a data layer.
2. Select units on the map (click, Ctrl / Cmd-click, Ctrl / Cmd-drag) or tick them in the **Units** list.
3. Set the date range or the matches, the time step (hour / day / week, or match window), and the chart mode: **Per Unit** or **Aggregate** (total or average; speed and occupancy layers are always averaged).
4. Press **Generate Chart**.

---

## Data sources

All data is public. Values are hourly unless noted.

### New York City

| Layer | Source |
|---|---|
| Subway ridership, by station and by area | [MTA Subway Hourly Ridership](https://data.ny.gov/Transportation/MTA-Subway-Hourly-Ridership-Beginning-2025/5wq4-mkjj/about_data) |
| Bus ridership, by route | [MTA Bus Hourly Ridership](https://data.ny.gov/Transportation/MTA-Bus-Hourly-Ridership-Beginning-2025/gxb3-akrn/about_data) |
| Bus stop boardings / alightings (May – Aug) | [MTA Bus Stop Level Ridership](https://data.ny.gov/Transportation/MTA-Bus-Stop-Level-Ridership-Beginning-2024/fvdm-uavx/about_data) |
| Bus network (routes, stops) | [MTA Bus Routes](https://data.ny.gov/Transportation/MTA-Bus-Routes/bzwk-3hb4/about_data), MTA Bus Stops |
| Citi Bike departures / arrivals | [Citi Bike System Data](https://citibikenyc.com/system-data) |
| Taxi and ride-hail pickups / dropoffs (Uber, Lyft, Yellow, Green) | [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) |
| Road speeds | [NYC DOT Traffic Speeds](https://data.cityofnewyork.us/Transportation/DOT-Traffic-Speeds/i4gi-tjb9/about_data) |
| EZ-Pass reader speeds | [EZ-Pass Readers](https://data.cityofnewyork.us/d/h47y-6hft) |
| Bike and pedestrian counts | [Bicycle and Pedestrian Counts](https://data.cityofnewyork.us/Transportation/Bicycle-and-Pedestrian-Count-Sensors/6up2-gnw8/about_data) |
| Bridge and tunnel crossings | [MTA Bridges and Tunnels Hourly Crossings](https://data.ny.gov/Transportation/MTA-Bridges-and-Tunnels-Hourly-Crossings-Beginnin/ebfx-2m7v/about_data) |
| Congestion relief zone entries (10 / 30 / 60 min) | [MTA Congestion Relief Zone Vehicle Entries](https://data.ny.gov/Transportation/MTA-Congestion-Relief-Zone-Vehicle-Entries-Beginn/t6yz-b64h/about_data) |
| Nightlife and accommodation POI | [OpenStreetMap](https://www.openstreetmap.org/), [Inside Airbnb](https://insideairbnb.com/get-the-data/) |
| Zone Function Atlas (floor-area mix, venues, viewing sites) | [MapPLUTO 26v1](https://www.nyc.gov/site/planning/data-maps/open-data/dwn-pluto-mappluto.page), NYS SLA liquor licenses, NYC DOHMH restaurant inspections, NYC fan-zone calendar |
| Boundaries | NYC Open Data (2020 census tracts, NTAs, CDTAs), NYC TLC taxi zones |

### Other cities

| City | Layer | Source |
|---|---|---|
| Seattle | Traffic counts, bike / pedestrian counters, paid parking occupancy | [Seattle DOT open data](https://data.seattle.gov/) |
| Los Angeles | Highway stations (flow, occupancy, speed) | [Caltrans PeMS](https://pems.dot.ca.gov/), District 7 |
| Los Angeles | Metro Bike Share | [Metro Bike Share data](https://bikeshare.metro.net/about/data/) |
| Bay Area | Highway stations | [Caltrans PeMS](https://pems.dot.ca.gov/), District 4 |
| Boston | Bluebikes | [Bluebikes System Data](https://bluebikes.com/system-data) |

### All cities

| Data | Source |
|---|---|
| Weather | [Open-Meteo historical weather API](https://open-meteo.com/) |
| Match schedule | FIFA World Cup 2026 fixtures |
| Basemap | © Esri |

Notes
- New York data is updated daily; other sources are updated as their publishers release new months.
- Highway station (PeMS) data on the site covers May – September of 2025 and 2026.
- Paid parking occupancy counts paid sessions, not parked cars.

Each source's own terms apply to its data.