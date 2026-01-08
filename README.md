# Vietnam War Downed Aircraft: Interactive Geospatial Map with POW/MIA and Commemorative Bracelets

An interactive web application mapping U.S. aircraft losses during the Vietnam War (1962–1973), with details on crash sites, crew fates (including MIA/POW status), and connections to Vietnam-era commemorative bracelets worn by civilians in support.

This project is personally motivated by my uncle, Robert Wayne Altus, who went Missing in Action (MIA) in Laos in 1971 while serving in the U.S. military. Through this work, I aim to honor his memory and highlight the stories of many like him whose fates remain unresolved, fostering education and remembrance.

**Author**: Troy Altus [](https://github.com/altustd)  
**Live Demo** (Planned): [Link to deployed app – coming soon]  
**Project Status**: In planning / early development (as of January 2026)

## Problem Statement

The Vietnam War resulted in thousands of U.S. aircraft losses and hundreds of servicemen listed as **Missing in Action (MIA)** or **Prisoners of War (POW)**, many of whose fates remain unresolved or deeply personal to families and veterans—like my uncle, Robert Wayne Altus, MIA in Laos (1971).

Historical data on these events is scattered across websites, archives, and databases, making it difficult for the public, researchers, educators, and families to explore spatially and contextually.

This project addresses this by creating an **interactive, clickable geospatial map** that visualizes downed aircraft locations, provides crew details and fate updates, and incorporates the human element of **POW/MIA commemorative bracelets** – a powerful civilian solidarity movement from the era.

The goal is educational and commemorative: to honor service, highlight unresolved cases, and make complex historical data accessible and engaging.

## Data

### Sources
- Aircraft losses: Vietnam Air Losses database, Aviation Archaeology, National Archives THOR dataset (Kaggle), DPAA records.
- POW/MIA status: Defense POW/MIA Accounting Agency (DPAA) database, Library of Congress POW/MIA lists, POW Network biographies.
- Bracelets: Museum collections (e.g., Air Mobility Command Museum, Palm Springs Air Museum), historical articles, public registries.
- Geospatial: Place names geocoded via OpenStreetMap/Nominatim; some sources provide approximate coordinates.

### Size
- Target: 5,000–10,000 aircraft loss incidents (full U.S. fixed-wing + helicopter losses).
- Initial MVP: ~1,000–2,000 well-documented cases (starting with USAF/USN).
- Crew records: ~10,000–20,000 individual entries.
- Bracelet links: Hundreds to thousands (where names match known MIA/POW).

### Key Features
- Crash date, location (lat/long or place name), aircraft type/serial, cause of loss.
- Crew names, ranks, outcomes (KIA, rescued, POW, MIA, later accounted-for).
- MIA/POW status updates (e.g., remains identified in 2020).
- Bracelet matches: Names that appeared on commemorative bracelets.

### Data Quality Issues
- Inconsistent location precision (many described as "near Hanoi" rather than exact coordinates → requires geocoding with potential error).
- Name variations and spelling differences → requires fuzzy matching.
- Incomplete crew fate data in some records.
- Bracelet data is fragmentary (no central database) → relies on museum scrapes and cross-references.

## Approach

### EDA
- Distribution of losses by year, branch, aircraft type, and region.
- Heatmaps of high-loss areas (e.g., Ho Chi Minh Trail, Route Packages in North Vietnam).
- Analysis of crew outcomes vs. location/year.

### Feature Engineering
- Geocoding place names to latitude/longitude.
- Fuzzy string matching to link aircraft incidents with POW/MIA records.
- Clustering crash sites for pattern detection.

### Models Used
- Primarily data processing and visualization (no predictive ML in MVP).
- Potential future: Clustering (DBSCAN) for hotspot identification; simple classification for loss cause inference.

### Validation Strategy
- Cross-reference multiple sources for each incident.
- Manual spot-checks against official DPAA updates.
- User feedback loop for corrections (planned).

## Results

*(In progress – early development stage)*

Expected key outputs:
- Interactive map with clickable markers showing incident details and crew pop-ups.
- Filters for year, service branch, status (MIA/POW only), aircraft type.
- Visualizations: Timeline of losses, outcome breakdowns, regional heatmaps.

Key findings (anticipated):
- Concentration of losses in specific corridors.
- High proportion of unresolved MIAs in Laos/Cambodia.
- Many bracelet names linked to long-term MIA cases.

## Tools & Technologies

- **Data Collection**: Python (requests, BeautifulSoup, Selenium for scraping).
- **Data Processing**: pandas, GeoPandas, geopy (geocoding).
- **Database**: SQLite (MVP) → PostgreSQL + PostGIS (for spatial queries).
- **Visualization**: Folium/Leaflet.js for interactive map, Plotly/Dash or Streamlit for dashboard.
- **Deployment**: Streamlit Sharing, Heroku, or GitHub Pages.
- **Version Control**: Git/GitHub.

## How to Run

*(To be updated as code is developed)*

1. Clone the repository:
   ```bash
   git clone https://github.com/altustd/vietnam-aircraft-losses-map.git
