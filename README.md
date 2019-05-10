# Polish Population in Ireland 2006-2016 on [map](https://gornymooj.github.io/polish.population.io/)

This map aims to show changes in the number of Polish people living in the Republic of Ireland in the years 2006 - 2016. This is presented via 5 interactive components of the web page: map, popups, scatter chart, bar chart and table. All those elements are linked together for better interactions with data and its understanding.

### Statistic Data
Tabular data is taken from the official website of the [Central Statistics Office(CSO)](http://census.ie/). The data was processed to unify schemas that slightly differ across each of the censuses. The information about the Polish minority living in Ireland was started to be recorded in 2006, after Poland joined the European community in May 2004. The population information was brought together into the one [CSV](https://github.com/gornyMooj/polish.population.io/blob/master/population_csv.csv) table. The process was carried manually in  MS Office and some its bits were automated using Python scripts (*OpenPyXL library read/write Excel files*).

### Spatial Data
Boundaries data was downloaded in the [shapefile](https://en.wikipedia.org/wiki/Shapefile) format. The data utilised in building the web map consists of the following datasets: [Counties](https://www.cso.ie/en/census/census2011smallareapopulationstatisticssaps/), [Electoral Divisions](https://www.cso.ie/en/census/census2011smallareapopulationstatisticssaps/). The data needed to be processed in order to display in the responsive way that composite geometries in the web browser. The most demanding was the Electoral Division ([ED](https://en.wikipedia.org/wiki/Electoral_division_(Ireland))) dataset which is the very complex file containing 3,399 polygons.
The data was reviewed and cleaned in QGIS, all unecessery columns were removed from the attribute tables to reduce the size of the shapefiles. Then using [GDAL's](https://www.gdal.org/) [ogr2ogr](https://gdal.org/1.11/ogr2ogr.html) tool their geopmetries were simplified and converted into the [TopoJSON](https://github.com/topojson/topojson) files. TopoJSON is an extension of GeoJSON that encodes topology. It is also is substantially more compact than GeoJSON, frequently offering a reduction of 80% or more even without simplification. Yet encoding topology also has numerous useful applications for maps and visualization above! It allows topology-preserving shape simplification, which ensures that adjacent features remain connected after simplification; this applies even across feature collections, such as simultaneous consistent simplification of state and county boundaries. 

### Technology and tools
The charts and map's lements were build using [D3.js](https://d3js.org/) and [leaflet.js](https://leafletjs.com/). With D3.js are handled the legend, charts, tabular data and Electoral Division dataset, where leaflet is used for the counties dataset and the basemaps.</b>
Below are listed all tools used in the building of this web application:
- D3.js V3
- leaflet.js V0.7
- jQuery
- Bootstrap 3
- DataTables a plug in for the jQuery
- TopoJSON
- GDAL
- QGIS
- MS Office
- Python 2.7 (OpenPyXL library)


