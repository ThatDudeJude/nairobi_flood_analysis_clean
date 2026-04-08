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

These factors were combined into a classified raster with four levels: low, slight, moderate and high susceptibility. The rationale behind the simple model can be found in ....

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

Results show that approximately 3.2 million people are xposed to flood risk, with around 277,000 in high-risk zones.

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

## Conclusion

Flood risk in Nairobi County is shaped by the interaction between terrain, river systems and human settlement patterns. While some areas have high total exposure, smaller, densely populated regions face more intense localized vulnerability.

This analysis provides a spatial foundation for flood risk planning and decision-making.
