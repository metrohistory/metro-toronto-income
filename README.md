# toronto-cma-income-areas
Toronto Census Metropolitan Area 2016 income map with case study areas

View map: https://metrohistory.github.io/toronto-cma-income-areas

Created by Ilya Ilyankou (https://www.picturedigits.com), Jack Dougherty (http://jackdougherty.org), and Jason Ellis (https://edst.educ.ubc.ca/facultystaff/jason-ellis/)

## Income census layer notes
- [Census Profile 2016, Statistics Canada](https://www12.statcan.gc.ca/census-recensement/2016/dp-pd/prof/details/page.cfm?Lang=E&Geo1=CMACA&Code1=535&Geo2=PR&Code2=01&SearchText=toronto&SearchType=Begins&SearchPR=01&B1=All&TABID=1&type=0)
- Median total income in 2015 among recipients ($ CAN)	for entire Toronto CMA = 31,705, which was used to normalize census tracts as below or above 100% of this level
- Inspired by https://thelocal.to/mapping-our-divisions

## Geodata sources and notes
- Used http://Mapshaper.org to reproject original shapefiles to WGS84 and edit features according to sources.
- Census tract boundaries 2016 were simplified in Mapshaper.org to reduce file size from 5MB to 1MB.
- Used Hans Hack Gimme Geodata tool http://hanshack.com/geotools/gimmegeodata to extract current and historical political boundaries in GeoJSON format from Open Street Map for areas that were dissolved into Toronto:
  - Etobicoke (background: last change to its boundaries (before it was dissolved completely) was in 1967, reflected in the 1971 decennial census maps: correspondended to tracts 200-250 (see gtf71cbk.pdf, page 27)
  - York (background: Township/later called Borough of York: corresponded to 1971 map tracts 150-176 (see gtf71cbk.pdf, page 26)
  - Scarbourough
- Reconstructed boundary for (Village of) Forest Hill from 1961 Canadian census (last time it appeared as separate municipality in decennial census): corresponded to tracts 150, 151, 152, and 153 in the 1961 census DLI files. *Does not align perfectly with other geodata but good enough for now*
