# Polish Population in Ireland 2006-2016 on [map](https://gornymooj.github.io/polish.population.io/)

This map aims to show changes in the number of Polish people living in the Republic of Ireland in the years 2006 - 2016. This is presented via 5 interactive components of the web page: map, popups, scatter chart, bar chart and table. All those elements are linked together for better interactions with data and its understanding.

### Statistic Data
Tabular data is taken from the official website of the [Central Statistics Office(CSO)](http://census.ie/). The data was processed to unify schemas that slightly differ across each of the censuses. The information about the Polish minority living in Ireland was started to be recorded in 2006, after Poland joined the European community in May 2004. The population information was brought together into the one [CSV](https://github.com/gornyMooj/polish.population.io/blob/master/population_csv.csv) table. The process was carried manually in  MS Office and some its bits were automated using Python scripts (*OpenPyXL library read/write Excel files*).

### Spatial Data
Boundaries data was downloaded in the [shapefile](https://en.wikipedia.org/wiki/Shapefile) format. The data utilised in building the web map consists of the following datasets: [Counties](https://www.cso.ie/en/census/census2011smallareapopulationstatisticssaps/), [Electoral Divisions](https://www.cso.ie/en/census/census2011smallareapopulationstatisticssaps/). The data needed to be processed in order to display in the responsive way that complex geometries in the web browser. The most demanding was displaying of the Electoral Division ([ED]() dataset which is the very complex file containing 3,399 polygons. 

### Technology used

