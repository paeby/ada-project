# Swiss Transit Isochrone Maps

## Abstract
Our project aims to provide intelligent visualizations of the contrast between spatial and temporal distance in Switzerland. We split the country into equal-sized hexagonal tiles and generate isochrone maps using any given tile as its starting point. This will allow the public to better understand its mobility potential, and restructure its thinking based on temporal and spacial information.

## Data Description
Our model will split Switzerland into equal-sized hexagonal tiles. We estimate the number of required tiles to be approximately 2500. We need to generate a square matrix of expected temporal distance from any tile to any tile. If necessary, due to constraints, we will limit the starting tiles to the most important areas.

The data can be obtained either distance by distance (1 cell at a time in the matrix) or in a more optimized fashion, the structure of the data permitting.

Among potential candidates for our datasource are
- Google Maps API ([Distance matrix API](https://developers.google.com/maps/documentation/distance-matrix/))
  - (2500 queries/day limit)
- [Swiss public transport API](http://transport.opendata.ch)
  - (3 queries/second limit)


## Feasibility and Risks
Our work will draw on the work of WNYC on [isochrone maps for New York City](https://imgur.com/yvgUbbe). We will use [QGIS](http://qgis.org/) with the [MMQGIS](http://michaelminn.com/linux/mmqgis/) plugin to generate the TopoJSON for the hexagonal tiles.

There are however some risks:
- The number of queries will be limited due to API constraints
- Uncertain reliability of the data, due to diversity of terrain (center of the tile might not be a feasible point of access for public transportation)

## Deliverables
A static web page which will allow users to visualize the isochrone map for any given starting point.

## Timeplan
We will work in parallel on gathering the data and the visualization.
- **[14.11.2016]** Determine whether the Swiss public transport API will be able to provide us with enough queries to gather our data.
- **[21.11.2016]** Build TopoJSON hexagon file for Swiss map
- **[21.11.2016]** Design strategy based on feasible APIs.
- **[12.12.2016]** Collect and clean data based on hexagon center points.
- **[10.01.2016]** Generate isochrone maps for collected data.
- **[17.01.2016]** Finalize project by displaying the maps on the web page.
