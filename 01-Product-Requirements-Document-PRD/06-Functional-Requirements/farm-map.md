# FR-04: Geospatial Farm Map

> **Module**: AgroScout AI PRD | **Status**: Approved Baseline

Requirements for geospatial visualization of parcels, scouting waypoints, and disease clusters.

## Requirements

1. Map shall display farm boundary polygons and parcel layers using GeoJSON / PostGIS vector tiles.
2. Scouting findings shall render as color-coded pins (Green = Healthy, Yellow = Warning, Red = Diseased).
3. Map shall support offline caching of vector and satellite tile layers for field use.
