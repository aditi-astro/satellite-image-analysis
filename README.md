# Satellite Image Analysis

A Python-based Earth observation project using Sentinel-2 satellite imagery to explore vegetation patterns near Kanpur, India.

## Project Overview

This project demonstrates a basic remote-sensing workflow using multi-spectral satellite data. Sentinel-2 Level-2A imagery is accessed through the Microsoft Planetary Computer STAC API and analyzed in Python.

## Completed Work

- Searched for Sentinel-2 L2A scenes using geographic bounds, acquisition dates, and cloud-cover criteria.
- Selected a scene acquired on 13 December 2025 with approximately 3.69% reported cloud cover.
- Used Rasterio to read satellite bands through a small window to limit memory usage.
- Generated satellite imagery visualizations using visible bands.
- Calculated the Normalized Difference Vegetation Index (NDVI) using the red and near-infrared bands.
- Visualized the NDVI distribution using a histogram and a range-based bar chart.
- Calculated summary statistics and the percentage of pixels in selected NDVI ranges.

## Preliminary Results

For the selected 512 × 512 pixel overview containing 262,144 valid pixels:

- Mean NDVI: approximately 0.158
- Median NDVI: approximately 0.149
- Standard deviation: approximately 0.085
- Pixels with NDVI from 0.1 to 0.2: 44.25%
- Pixels with NDVI from 0.2 to 0.4: 27.86%
- Pixels with NDVI from 0.4 to 1.0: 0.74%
- Pixels with NDVI below 0.1: 27.15%

These statistics describe the selected image overview, not the entirety of Kanpur.

## Tools and Technologies

- Python
- NumPy
- Matplotlib
- Rasterio
- pystac-client
- Microsoft Planetary Computer STAC API
- Sentinel-2 Level-2A imagery
- Google Colab
- Git and GitHub

## Methodology

NDVI is calculated as:

**NDVI = (NIR − Red) / (NIR + Red)**

For Sentinel-2 imagery, Band 8 (B08) provides near-infrared data and Band 4 (B04) provides red-band data.

## Limitations

- The analysis uses one acquisition date and does not establish seasonal trends.
- NDVI values alone cannot definitively identify land-cover classes.
- Results are based on a 512 × 512 pixel overview of the selected study area.
- Surface moisture, soil background, atmospheric effects, and vegetation conditions can influence NDVI.

## Future Work

- Compare vegetation indices across multiple acquisition dates.
- Improve true-colour and false-colour visualizations.
- Investigate spatial patterns in vegetation.
- Explore land-cover classification and additional remote-sensing indices.

## Reproducibility

The analysis notebook is available here:

[`01_satellite_image_analysis.ipynb`](./01_satellite_image_analysis.ipynb)

The notebook uses publicly available satellite imagery. Re-running it may require an internet connection and installation of the required Python packages.

## Data Source

- [Microsoft Planetary Computer](https://planetarycomputer.microsoft.com/)
- [Sentinel-2 documentation — European Space Agency](https://sentinels.copernicus.eu/web/sentinel/missions/sentinel-2)

## Author

Aditi Singh
