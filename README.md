# Layers Extraction from Draft Land Use Plan for Delhi 2041 (Work In Progress)
Delhi Development Authority recently [released](https://dda.org.in/hotlinks.aspx) draft land use plan 2041 for Delhi and called for public comments. This repo has some of the geospatial layers that I was able to extract from the PDF map of the [draft plan](http://119.226.139.196/tendernotices_docs/aug2020/Draft%20Land%20Use%20Plan_public%20notice09062021.pdf). The commands used for extraction are in the [bat](https://github.com/rajesvariparasa/layers_draft_delhi_master_plan_2041/blob/main/ExtractLayers.bat) file. Command `ogrinfo draftplan.pdf > layers.txt` was used to obtain all the layer names from the PDF.

## Layers fully extracted (QC pending)
1. BASE_MAP_2041_COMMERCIAL
2. BASE_MAP_2041_INDUSTRIAL
3. BASE_MAP_2041_RESIDENTIAL
4. Boundaries_DDA_ZONE_Boundary
5. Boundaries_LUTYEN_BUNGALOW_ZONE
6. Boundaries_RESERVED_FOREST_BOUNDARY
7. EXTRA_LAYERS_Builtup
8. EXTRA_LAYERS_FLOODPLAIN
9. EXTRA_LAYERS_LALDORA_GREENBELT_VOID_FILL
10. ROAD_RAILWAY_METRO_LINES_Barapulla_Elevated_Road
11. ROAD_RAILWAY_METRO_LINES_DMRC_Metro_Line
12. ROAD_RAILWAY_METRO_LINES_HSR_Alignment
13. ROAD_RAILWAY_METRO_LINES_NH_buffer
14. ROAD_RAILWAY_METRO_LINES_Railway_Lines
15. ROAD_RAILWAY_METRO_LINES_RRTS
16. ROAD_RAILWAY_METRO_LINES_UER_BUFFER

## Layers partially extracted
1. BASE_MAP_2041_GREEN_BELT_WATERBODY_1
2. BASE_MAP_2041_PSP_1
3. BASE_MAP_2041_RECREATIONAL_1
4. BASE_MAP_2041_TRANSPORTATION_1
5. BASE_MAP_2041_UTILITY_1

## Layers yet to be extracted
1. BASE_MAP_2041_GOVERNMENT
2. EXTRA_LAYERS_Delhi_UC
3. EXTRA_LAYERS_LDRA_VILLAGE
4. ROAD_RAILWAY_METRO_LINES_Roads_ROW_MPD_170321__query_applied

# Geospatial PDFs or GeoPDFs
Quite a few local development authorities have started using GIS for compiling the spatial information they collect for planning related surveys and activities. The tools such as ArcMap (ArcGIS' Desktop) or QGIS, usually allow exporting these layers as PDF maps. These PDFs are most often geospatial PDFs that retain the spatial information and the vector geometries of the constitutent layers. One can view the coordinate information in these PDFs by opening them in a software such as Adobe Acrobat and using the 'Tools> Measure> Geospatial Location Tool' option. This is also one way of verifying if the PDF is a geospatial PDF. This ability of the file format -to retain spatial info- allows extraction of the constituent layers back from the PDFs for any further analysis. However, such an extraction process is still not ideal since the attribute information, such as labels/names of the features, are difficult to extract. And one also has to deal with projection/coordinate system related discrepancies that arise as a result of such extraction.

Till departments start sharing spatial data in usable formats, these workarounds should be of some help.
