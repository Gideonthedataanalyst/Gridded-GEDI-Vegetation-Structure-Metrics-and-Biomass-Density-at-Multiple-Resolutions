# Gridded-GEDI-Vegetation-Structure-Metrics-and-Biomass-Density-at-Multiple-Resolutions

![Screenshot (46)](https://github.com/user-attachments/assets/b2a53238-bf37-47f5-9921-6bf2f81ddfd9)


This script demonstrates how to use the GEDI (Global Ecosystem Dynamics Investigation) gridded vegetation structure data in Google Earth Engine (GEE) to analyze vegetation metrics across Nairobi, Kenya, from 2019 to 2023. Here's an explanation of its key components and how they relate to Nairobi:

1. Metrics Explained
GEDI provides detailed vegetation metrics based on lidar data from spaceborne sensors. For Nairobi, these metrics include:

1.1 ssmean (Shot Metric Mean)
The average value of GEDI shot metrics within a pixel, representing vegetation characteristics like canopy height or density.

1.2 meanbse (Bootstrap Standard Error)
Reflects the uncertainty in the mean, derived through bootstrap resampling (100 samples, each with 70% of shots). It ensures reliability when at least 10 shots exist within a grid cell.

1.3 median (Median Value)
The 50th percentile of GEDI shot metric values, providing a robust central tendency measure for vegetation height or density.

1.4 sd (Standard Deviation)
Shows variability in GEDI shot metrics, reflecting heterogeneity in Nairobi's vegetation structure.

1.5 iqr (Interquartile Range)
The difference between the 75th and 25th percentiles, offering insights into the spread of vegetation height or density.

1.6 p95 (95th Percentile)
Represents the height of the tallest vegetation in 95% of the shots, useful for identifying dominant canopy structures.

1.7 shan (Shannon’s Diversity Index)
Measures the diversity of vegetation heights using GEDI shot metrics, emphasizing Nairobi's ecological complexity.

1.8 countf (Filtered Shot Count)
Counts GEDI shots per pixel after filtering for quality and temporal acquisition criteria, ensuring accuracy in vegetation analysis.

2. Nairobi Boundary Setup
The FAO/GAUL dataset is filtered for Nairobi (e.g., ADM1_NAME = 'Nairobi') to focus analysis on its boundary.

3. GEDI Data
The script uses GEDI image collections at varying resolutions:

1KM, 6KM, and 12KM grids enable analyzing vegetation metrics at different spatial scales.
Nairobi's compact urban area benefits from finer 1KM resolution for localized insights.
4. Slopeshade Basemap
Elevation Data: Comes from the MERIT DEM dataset.
Slope Map: Generated using ee.Terrain.slope(), visualizing Nairobi's terrain variability.
Visualization: Grayscale palette (white to black) highlights topographic features like hills and valleys.
5. Shot and Orbit Metrics (2019–2023)
Key metrics derived from GEDI Counts dataset (COUNTS/V1/1KM):

Shots Count: Total GEDI shots per 1KM pixel, indicating data density.
Unique Orbits: The number of unique satellite passes, representing data reliability.
Nearest Neighbor Index (NNI): Measures spatial clustering of shots to assess uniformity.
6. Vegetation Structure Metrics (RH98)
RH98 (Relative Height 98):

Represents the 98th percentile canopy height, an indicator of maximum vegetation height.
Thresholds: Minimum height ≥ 3m, with ≥ 10 valid shots.
Standard Deviation (SD): Reflects vegetation height variability across Nairobi's diverse landscapes, from urban parks to natural reserves like Karura Forest.

7. Foliage and Density Metrics
FHD (Foliage Height Diversity):

Derived from the 1m vertical Plant Area Index (PAI) profile.
Median FHD values between 1.2 and 3.2 highlight vegetation complexity.
PAVD (Plant Area Volume Density):

Represents the height above ground where the peak PAVD occurs.
Useful for understanding vegetation density distribution across urban and peri-urban areas.
8. Visualization
Clipping to Nairobi: All layers are clipped to Nairobi’s boundary for precise analysis.
Opacity: Managed using the opac variable (default 0.7) for better visualization of overlapping datasets.
9. Higher-Resolution GEDI Data (6KM Pixels)
For areas with sparse 1KM coverage, like low-density regions within Nairobi, 6KM resolution provides more continuous data.

Practical Applications for Nairobi
Urban Ecology:
Insights into vegetation height and diversity can inform urban forestry and green space management.

Climate Adaptation:
Understanding vegetation structure helps assess Nairobi’s resilience to urban heat and its role in climate regulation.

Biodiversity Conservation:
Metrics like RH98 and FHD can guide conservation efforts in areas like Karura Forest and Nairobi National Park.

Urban Planning:
Data-driven approaches to integrating green spaces into urban development plans.

This script leverages GEDI's data richness to explore Nairobi's vegetation dynamics comprehensively. Let me know if you'd like to discuss specific implementations!
