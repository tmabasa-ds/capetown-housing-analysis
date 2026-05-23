# Cape Town's Disappearing Rentals: Mapping the Airbnb Effect

A geospatial data analysis examining the impact of short-term rental platforms on Cape Town's housing market, with a focus on displacement pressure in working-class suburbs and the role of the growing digital nomad economy.

**Live analysis:** [Read the full writeup](capetown_analysis_narrative.md)

---

## What this project is about

Cape Town has 26,877 Airbnb listings. 82.6% of them are entire homes (not spare rooms, but entire properties withdrawn from the long-term rental market). The median listing costs R1,526 per night, or roughly R45,780 a month. The median monthly salary in the Western Cape is approximately R8,500.

This project maps where that pressure is concentrated, which communities are absorbing the cost, and what the gap between Airbnb pricing and local affordability actually looks like when you put it on a map.

---

## Key findings

- **2,696 entire homes** have been removed from Cape Town's City Centre long-term rental market alone
- **Clifton is 99.5% entire-home listings.** Essentially the entire suburb's Airbnb stock is full properties, not rooms
- The median Airbnb monthly equivalent in **Camps Bay is R141,750**, more than 16x the median local salary
- **Woodstock**, historically a working-class coloured neighbourhood, now has 412 listings at a median monthly equivalent of R27,930. Long-term rents in the same area were R4,000 to R6,000 a decade ago
- The **Cape Flats and eastern suburbs** barely register on the Airbnb map. The platform's geography of desirability mirrors the city's historical racial geography

---

## Maps and visualisations

| Output | Description |
|--------|-------------|
| `outputs/airbnb_pressure_map.html` | Interactive choropleth: entire homes removed from the long-term market by suburb |
| `outputs/airbnb_price_map.html` | Interactive choropleth: median nightly Airbnb price by suburb |
| `outputs/affordability_gap.png` | Bar chart comparing Airbnb monthly equivalents to local salary benchmarks |

---

## Project structure

```
capetown-housing-analysis/
├── data/
│   ├── listings.csv              # Inside Airbnb, 26,877 listings (Sept 2025)
│   └── Official_Suburb.geojson  # City of Cape Town suburb boundaries
├── notebooks/
│   └── 01_data_exploration.ipynb
├── outputs/
│   ├── airbnb_pressure_map.html
│   ├── airbnb_price_map.html
│   └── affordability_gap.png
└── capetown_analysis_narrative.md
```

---

## Stack

- **Python:** pandas, geopandas, folium, matplotlib, seaborn
- **Data sources:** [Inside Airbnb](http://insideairbnb.com/cape-town), [City of Cape Town Open Data Portal](https://odp-cctegis.opendata.arcgis.com)
- **Tools:** Jupyter Notebook, VSCode

---

## How to run it

```bash
git clone https://github.com/tmabasa-ds/capetown-housing-analysis
cd capetown-housing-analysis
python -m venv venv
venv\Scripts\activate  # Windows
pip install -r requirements.txt
```

Download the data:
- `listings.csv` from [insideairbnb.com/cape-town](http://insideairbnb.com/cape-town). Select the most recent date, download `listings.csv.gz`, then unzip it
- `Official_Suburb.geojson` from the [City of Cape Town Open Data Portal](https://odp-cctegis.opendata.arcgis.com)

Place both files in the `data/` folder, then open `notebooks/01_data_exploration.ipynb`.

---

## On the digital nomad question

South Africa introduced a Digital Nomad Visa in 2024. The economic argument for it is real. Attracting remote workers who earn in foreign currency does bring spending into the local economy. But the cost of that policy is not distributed equally. It shows up in housing markets, in suburb-by-suburb displacement, in families pushed further from the city centre.

This project does not argue that digital nomads are the sole cause of Cape Town's housing crisis. The roots of that go much deeper. But the data shows clearly that short-term rental platforms operating at scale and with minimal regulation are accelerating a displacement pattern that was already underway, and the communities paying the price are the ones with the least power to push back.

---

## Author

**Tiyani Mabasa** | Data Scientist, Full-Stack Developer, Johannesburg  
[cosmocribs.co.za](https://cosmocribs.co.za) · [linkedin.com/in/tiyanimabasa](https://linkedin.com/in/tiyanimabasa) · tiyani78@gmail.com

---

*Data sourced from Inside Airbnb (September 2025) and the City of Cape Town Open Data Portal. All code and analysis is original work.*
