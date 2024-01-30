Disclaimer: Please compare the data layers with the official PDF before using the data in your own project.

An interactive tool to visualise layers extracted so far can be viewed [here](https://draftmpd41.github.io/) developed by [Nikhil VJ](https://nikhilvj.co.in/).

# Layers Extraction from Draft Land Use Plan for Delhi 2041 (Work In Progress)
Delhi Development Authority recently [released](https://dda.org.in/hotlinks.aspx) draft land use plan 2041 for Delhi and called for public comments. This repo has some of the geospatial layers that I was able to extract from the PDF map of the [draft plan](http://119.226.139.196/tendernotices_docs/aug2020/Draft%20Land%20Use%20Plan_public%20notice09062021.pdf). The commands used for extraction are in the [bat](https://github.com/rajesvariparasa/layers_draft_delhi_master_plan_2041/blob/main/ExtractLayers.bat) file. Command `ogrinfo draftplan.pdf > layers.txt` was used to obtain all the layer names from the PDF.

## Other notes
When these layers were imported into QGIS, noticed that five of the extracted layers presented with a peculiar problem - all the geometries of these layers seemed distorted (image below). This could possibly be because of the 'shading' style used to represent the layer while making the PDF. The challenge was to eleminate the lines so the geometries underneath could be filtered in. Used the 'Select features using expression' option and used the expression `num_points($geometry)=2` to select all the shading lines. Then, inverted the selection to select all the neat geometries and exported them in a separate file.

<center><img src="https://github.com/rajesvariparasa/layers_draft_delhi_master_plan_2041/blob/main/DistortedLayerCorrection.png" width="600"/></center>

![alt text](https://github.com/draftmpd41/draftmpd41.github.io/blob/main/screenshot.png "Interactive Snapshot")


## Extraction status of the layers

#### Layers fully extracted (QC pending)
1. BASE_MAP_2041_COMMERCIAL
2. BASE_MAP_2041_INDUSTRIAL
3. BASE_MAP_2041_RESIDENTIAL
4. BASE_MAP_2041_TRANSPORTATION (split as BASE_MAP_2041_TRANSPORTATION_1 and BASE_MAP_2041_TRANSPORTATION_2)
5. BASE_MAP_2041_UTILITY (split as BASE_MAP_2041_UTILITY_1 and BASE_MAP_2041_UTILITY_2)
6. BASE_MAP_2041_GREEN_BELT_WATERBODY_1
7. BASE_MAP_2041_GOVERNMENT
8. BASE_MAP_2041_PSP_1
9. BASE_MAP_2041_RECREATIONAL_1
10. Boundaries_DDA_ZONE_Boundary
11. Boundaries_LUTYEN_BUNGALOW_ZONE
12. Boundaries_RESERVED_FOREST_BOUNDARY
13. EXTRA_LAYERS_Builtup
14. EXTRA_LAYERS_FLOODPLAIN
15. EXTRA_LAYERS_LALDORA_GREENBELT_VOID_FILL
16. EXTRA_LAYERS_Delhi_UC
17. EXTRA_LAYERS_LDRA_VILLAGE
18. ROAD_RAILWAY_METRO_LINES_Barapulla_Elevated_Road
19. ROAD_RAILWAY_METRO_LINES_DMRC_Metro_Line
20. ROAD_RAILWAY_METRO_LINES_HSR_Alignment
21. ROAD_RAILWAY_METRO_LINES_NH_buffer
22. ROAD_RAILWAY_METRO_LINES_Railway_Lines
23. ROAD_RAILWAY_METRO_LINES_RRTS
24. ROAD_RAILWAY_METRO_LINES_UER_BUFFER

#### Layers yet to be extracted
1. ROAD_RAILWAY_METRO_LINES_Roads_ROW_MPD_170321__query_applied
2. Labels

#### Data loss
Extraction of geospatial data from PDFs almost always results in some form of data loss. Even if all geometries are extracted, the attribute information is lost. For this exercise, I could not extract the 'labels' layer which contained the names/titles of each geographic feature in the PDF map. I also couldn't extract the category of feature. For instance, the layer 'Public & Semi Public Facilities' has 8 categories. However, this is not retained in the extracted layers. 

# Geospatial PDFs or GeoPDFs
Quite a few local development authorities have started using GIS for compiling the spatial information they collect for planning related surveys and activities. The tools such as ArcMap (ArcGIS Desktop) or QGIS, usually allow exporting these layers as PDF maps. These PDFs are most often geospatial PDFs that retain the spatial information and the vector geometries of the constitutent layers. One can view the coordinate information in these PDFs by opening them in a software such as Adobe Acrobat and using the 'Tools> Measure> Geospatial Location Tool' option. This is also one quick way of verifying if the PDF is a geospatial PDF. This ability of the file format -to retain spatial info- allows extraction of the constituent layers back from the PDFs for any further spatial analysis. However, such an extraction process is still not ideal since the attribute information, such as labels/names of the features, are difficult to extract. And one also has to deal with projection/coordinate system related discrepancies that arise as a result of such extraction.

Till departments start sharing spatial data in usable formats, these workarounds should be of some help.
