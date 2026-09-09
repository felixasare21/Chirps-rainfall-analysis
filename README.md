# CHIRPS Rainfall Analysis over Ghana (2010–2020)

This repository contains a Python/Jupyter Notebook workflow for analyzing daily CHIRPS precipitation over Ghana from 2010 to 2020.

## Analyses included

- Monthly rainfall climatology
- Seasonal rainfall climatology
- Regional monthly rainfall climatology
- Regional mean annual rainfall
- SPI-12 drought and wetness analysis
- Pixel-wise Mann–Kendall trend testing and Sen's slope
- Rainfall onset and cessation
- Length of Growing Period (LGP)

## Data

The analysis uses **CHIRPS Version 2.0** precipitation data and Ghana administrative boundary data.

The source NetCDF and boundary files are intentionally not included in this cleaned notebook package. Place them in:

```text
data/
├── Ghana_chirps.nc
└── boundaries/
    ├── gadm41_GHA_1.shp
    ├── gadm41_GHA_1.shx
    ├── gadm41_GHA_1.dbf
    └── gadm41_GHA_1.prj
```

The complete shapefile set is required for GeoPandas to read the boundary data correctly.

## Main notebook

Open:

`chirps_github_ready.ipynb`

The notebook is organized into clear sections for data loading, preprocessing, climatology, drought analysis, trend analysis, and agro-climatological metrics.

## Requirements

Install the required Python packages with:

```bash
pip install -r requirements.txt
```

## Outputs

Generated figures and tables are written to the `outputs/` directory.

## Notes

The rainfall onset and cessation calculations use threshold-based definitions:

- Onset: first 3-day rainfall total ≥ 20 mm after day 60 of the year.
- Cessation: last qualifying 3-day rainfall total ≥ 10 mm between days 240 and 334.
- LGP: cessation day minus onset day.

These thresholds should be explicitly justified if the analysis is used in an academic publication.

## Citation

CHIRPS was developed by the Climate Hazards Center at the University of California, Santa Barbara. Cite the CHIRPS dataset and relevant CHIRPS documentation when using this work.

## Author

Kwadwo Okoto
