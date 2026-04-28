# Aproach and Justification

Flooding is a recurring risk in urban areas with complex terrain and dense populations. Nairobi County presents a mix of low-lying regions, river systems and rapidly-growing settlements, making it an ideal case for spatial flood risk analysis.

This project aims to assess flood susceptibility and evaluate its impact on infrastructure and population. In this notebook, I document how I developed and presented the rationale behind the susceptibility model and how exposure was determined using the QGIS tool.

 ## The Susceptibility Model

A binary classification approach was used for elevation, slope and river proximity to maintain model simplicity and interpretability. While reclassification into multiple categories is possible, it was avoided to reduce subjectivity and prevent overcomplicating the model without strong empirical justification.

### 1.  Elevation Threshold selection
The elevation threshold of $<1750\ m$ was selected to capture low-lying areas across Nairobi's west-east elevation gradient. Since river elevations vary significantly across the county, elevation alone was not used as a strict determinant. Instead, it was combined with slope and proximity to rivers to better represent flood susceptibility.

```
low_elevation_area = DEM < 1750 (threshold)
```

### 2. Slope Threshold selection
The slope threshold $<3^\degree$ was selected based on sampled values along the Nairobi River and tributary corridors (~$1^\degree-2^\degree$) and the overall slope distribution (mean ~ $3.6^\degree$), ensuring that only relatively flat areas - where water accumulation is most likely - are classified as flood-prone.

```
water_accumulation_zone = slope < 3 degrees
```


### 3. River Proximity Threshold selection
The threshold distance from rivers $<200\  m$ was chosen to ensure that it follows rivers, expands into a realistic floodpain and would include tributaries while avoiding covering huge areas.

```
rive_flooding_zone = distance_from_river < 200
```


Therefore, susceptibility was modeled using a simple additive approach combining low elevation, low slope and proximity to rivers, producing a 0-3 index representing increasing environmental risk.

```
susceptibility = elevation + slope + river_distance
```

Validation using known flood-prone areas such as Kibra showed that the model correctly identifies high susceptibility in low-lying, river-adjacent zones while excluding higher elevation areas with fewer hydrological features.

Broad susceptibility analysis ($\ge 2$) indicates that approximately 61% of buildings fall within environmentally vulnerable zones.

However, when restricting to high-confidence zones ($value = 3$), the proportion of exposed buildings is significantly lower, highlighting the sensitivity of results to threshold selection.

