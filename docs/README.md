## Title: Flood Risk and Exposure Analysis for Nairobi County

## Overview
This project analyzes flood risk across Nairobi County by combining terrain characteristics, hydrological factors and exposure data. The goal is to identify areas that are most vulnerable to flooding and pinpoint which infrastructure and section of the population are affected based on location.

The analysis is structured into four key components: Flood susceptibility, infrastructure exposure, population exposure and hotspot identification.

## Objectives
- Identify areas prone to flooding using terrain and river proximity.
- Assess infrastructure exposed to flood risk.
- Estimate the population living in flood-prone areas.
- Highlight critical hotspots where risk and exposure overlap.

## Data Sources
- OpenStreetMap (buildings, roads, schools, hospitals) [1]
- WorldPop (population data) [2]
- DEM (elevation data) [3]

## Methodology
### 1. Flood Susceptibility
Flood susceptibility was derived using three main factors: elevation, slope and proximity to rivers.

- Low elevation areas were considered more prone to flooding.
- Flat terrain areas were less likely to drain accumulated water.
- Areas near rivers were assigned a higher risk.

These factors were combined into a classified raster with four levels: low, slight, moderate and high susceptibility. The rationale behind the simple model can be found [here](./SUSCEPTIBILITY_MODEL_RATIONALE.md)

### 2. Infrastructure Exposure
Infrastructure layers (buildings, roads, schools and hospitals) were overlaid with flood susceptibility zones.

- Buildings within flood-prone areas were extracted and counted.
- Roads were assessed based on segments intersecting high-risk zones.
- Schools and hospitals were identified within exposed regions.

This step highlights the physical assets at risk.

### 3. Population Exposure
Population exposure was estimated by combining flood susceptibility zones with gridded population data.

- NoData values were handled and filled appropriately.
- Population within flood-prone areas was calculated

Results show that approximately 3.2 million people are exposed to flood risk, with around 277,000 in high-risk zones.

## Hotspot Analysis
Hotspots were identified by combining:
- High flood susceptibility.
- High infrastructure exposure.
- High population density.

This allowed identification of areas with the greatest potential impact.

## Key Findings

- Flood risk is concentated along river corridors and low-lying terrain.
- A significant portion of infrastructure is located in flood-prone areas.
- Population exposure is highly concentated in dense settlements.
- Areas such as Kibra nad Mathare show intense localized vulnerability.
- Larger sub-counties show higher total exposure due to spatial extent.

## Maps Included
1. Flood Susceptibility Map
![Flood Susceptibility Map](../outputs/maps/Flood%20Susceptibility.png)
2. Infrastructure Exposure Map.
![Infrastructure Exposure Map](../outputs/maps/Infrastructure%20Exposure.png)
3. Population Exposure Map.
![Population Exposure Map](../outputs/maps/Population%20Exposure.png)
4. Flood Hotspot Map.
![Flood Hotspot Map](../outputs/maps/Flood%20Hotspots.png)

Each map answers a specific question and contributs to the overall analysis.

## Tools Used
- QGIS 3.40
- Raster analysis tools.
- Vector overlay and spatial queries.

## Project (Structure)
This project follows a structured workflow to seperate raw data, processing steps and final outputs.

The original working structure is organzed as follows:

- __data/__
  Contains all datasets used in the analysis
  - raw/ &rarr; original input data (DEM, buildings, population, etc.)
  - interim/ &rarr; intermediate outputs generated during processing.
  - processed/ &rarr; cleaned and final datasets used in analysis.
- __qgis/__
  Contains the QGIS project file used to perform the analysis and generate maps.
- __outputs/__
  Contains all final outputs
  - maps/ &rarr; final map layouts exported as images
  - figures/ &rarr; supporting visuals
  - tables/ &rarr; summarized results
- __docs/__
  Contains project documentation, including this README

### Repository Note
Due to the file size limitations, the full dataset is not included in this repository. The GitHub version contains ony the final outputs and project files necessary to understand and reproduce the analysis workflow.

## Data Access & Reproducibility
### Data Access
The complete dataset used in this project (~1.7 GB) is hosted externally due to GitHub storage limitations.
You can access the data here: [Nairobi Flood Analysis Files](https://drive.google.com/drive/folders/1SZaQwstIExvcp7Cj0GFstHHGzk7LuOLP?usp=sharing)
 

### Reproducibility
To reproduce the analysis:
1. Download the full dataset from the link above.
2. Place the data folder in the root project directory so that the structure matches the original layout.
3. Open QGIS project file located in the ```qgis/```folder.
4. Ensure all data paths are correctly linked (you may need to relink layers if paths change).

### Notes
- The analysis was conducted using __QGIS 3.40__.
- Raster and vector processing tools were used to generate susceptibility, exposure and hotspot layers.
- Intermediate datasets are included in the external data package for transparency and reproducibility.



## Conclusion

Flood risk in Nairobi County is shaped by the interaction between terrain, river systems and human settlement patterns. While some areas have high total exposure, smaller, densely populated regions face more intense localized vulnerability.

This analysis provides a spatial foundation for flood risk planning and decision-making.
