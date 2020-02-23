# toronto-cma-income-areas
Toronto CMA income map with case study areas

## Jack's notes for Ilya

Tip: This is my new favorite tool for grabbing GeoJSON boundaries from Open Street Map data: http://hanshack.com/geotools/gimmegeodata/


Goal: create a Leaflet interactive map of metro Toronto with these layers:

1) Case study areas (toggle each on/off in legend, display transparent polygons, with thick colored boundary, choose different color for each and display color next to name in legend, similar to https://jackdougherty.github.io/bikemapcode/newbritain.html)
  - See each boundary file in `data` subfolder
  - Etobicoke (etobicoke-boundary-osm.geojson)
  - Forest Hill (forest-hill-boundary-1961-dli.geojson) *borders not perfectly aligned, but use for now*
  - York (york-boundary-osm.geojson)
  - Scarborough (scarborough-boundary-osm.geojson) *in case Jason and I wish to use it in future*

2) Toronto CMA (Census Metropolitan Area, aka Greater Toronto Area GTA) will appear as the exterior boundary (toronto-cma-boundary-2016-dli.geojson), but do not list in legend, no toggle

3) Individual personal income as percentage of Toronto CMA Average, by census tract, for either 2016 or 2011 (see details below). List in legend, toggle on/off to display thematic choropleth polygon map with divergent colors similar to https://thelocal.to/mapping-our-divisions, but 2D, not 3D)

4) Basemap layer = CartoDB positron with labels

About the average income by census tract layer:



census.csv -- use COL 18: Income of individuals in 2010 (part 1) - Both sexes / Total income in 2010 of population aged 15 years and over; Both sexes / Median income $; Both sexes

## Jason's notes

Files and folders and notes:

DLI 2011 Census… Should include all geospatial data for Toronto CMA (census metropolitan area). Might include all CMA data for the entire country! If it does, then Jack/Ilya will have to select the shape files corresponding to the Toronto CMA and make a Toronto base map. Tract level boundary files will be here, corresponding to the data below.

Census.csv… Raw, data for Toronto CMA, income variables only. Extracted from census analyzer. Legend at top indicates tract names for Toronto that will correspond to shape files in above.
However, note that the income data is from the 2011 National Household Survey, not the 2011 Census of Canada (which did not collect household income data). Here’s a good explanation of the differences between the National Household Survey and the Census of Canada: https://guides.library.ubc.ca/gpcanadacensus/censusNHS

I was unable to find shape files for Forest Hill, York, and Etobicoke. However, we can construct these by the back door, using different corresponding census tract shape files that are available. Here’s what I recommend:

To make shape files for Forest Hill:
-	The last Canadian decennial census year Forest Hill existed as a separate municipality was 1961.
-	(the Village of) Forest Hill corresponded to tracts 150, 151, 152, and 153 in the 1961 census (see Forest Hill census tracts 1961.png.)
-	Extract the shape files from DLI 1961 Census… for tracts 150, 151, 152, and 153 and use these to mark a Forest Hill layer on the Toronto base map

To make shape files for Etobicoke:
-	The last change to Etobicoke’s boundaries (before it was dissolved completely) was in 1967, reflected in the 1971 decennial census maps.
-	In the 1971 maps, Etobicoke corresponded to tracts 200-250 (see gtf71cbk.pdf, page 27)
-	Extract the shape files from DL 1971 Census… for tracts 200-250.

Ditto for (The Township) of York (aka The Borough of York) (nb not York County; not York Region, not the Borough or Township of North York; not the Borough or Township of East York. Not York University. Just “York (Township/later called Borough of York”. Toronto has too many Yorks, by far)
-	In 1971 maps York corresponded to tracts 150-176 (see gtf71cbk.pdf, page 26)
-	Extract the shape files from DL 1971 Census… for tracts 150-176
