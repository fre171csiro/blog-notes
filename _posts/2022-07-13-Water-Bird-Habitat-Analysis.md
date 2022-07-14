---
toc: true
layout: post
description: Overview of generating a raster (Cloud Optimised GeoTiff, COG) spatial layer to identify potential Water Bird Habitat in the Murray-Darling Basin.
categories: [markdown]
title: Water Bird Habitat Identification
show_image: 
show_tags: true
---
# Ecosystem Function - Water Bird Habitat Identification for Murray-Darling Basin

## Inputs
Bi Monthly Inundation layers, [FwDET data](https://data.csiro.au/collection/csiro:50243){:target="\_blank"} (25m resolution; MDB extent; bi-monthly time-step; 1988-2020)

## Description of methods
- Focal Statistic (sum) is executed for each valid pixel and each time-step of the bi-monthly inundation data, [FwDET](https://data.csiro.au/collection/csiro:50243){:target="\_blank"}
- 'Valid pixels': values are calculated for all pixels covered by water or within 500m of water coverage.
    - Options to buffer (500m) around each pixel with any water
- Return nodata for all pixels that are not 'valid pixels'.
- For all valid pixels, return the area (in hectares or cell counts) within the specified radius, that is covered by water that is within the specified inundation depth range.
- Two radii are applied:
    1. 3 km
    1. 20 km
- Two water depth ranges are applied:
    1. 0.5 to 1.0 m depth
    1. 0.5 to 1.5 m depth
- The combination of neighbourhood radii and depth range mean there will be four output products, each at the bi-monthly time-step.
## Outputs
[Bi Monthly layers](https://data.csiro.au/collection/csiro:55490){:target="\_blank"} for area of waterbird habitat (~100m resolution; MDB extent; bi-monthly time-step; 1988-2020) - in as similar file / folder format / structure & naming convention to the inundation data as possible.

