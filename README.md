# Layers Extraction from Draft Land Use Plan for Delhi 2041
Delhi Development Authority recently [released](https://dda.org.in/hotlinks.aspx) draft land use plan 2041 for Delhi and called for public comments. This repo has some of the geospatial layers that I was able to extract from the PDF map of the [draft plan](http://119.226.139.196/tendernotices_docs/aug2020/Draft%20Land%20Use%20Plan_public%20notice09062021.pdf). The commands used for extraction are in the [bat](https://github.com/rajesvariparasa/layers_draft_delhi_master_plan_2041/blob/main/ExtractLayers.bat) file. Command `ogrinfo draftplan.pdf > layers.txt` was used to obtain all the layer names from the PDF.

# Geospatial PDFs or GeoPDFs
Quite a few local development authorities have started using GIS for compiling the spatial information they collect for planning related surveys and activities. The tools such as ArcMap (ArcGIS' Desktop) or QGIS, usually allow exporting these layers as PDF maps. These PDFs are most often geospatial PDFs that retain the spatial information and the vector geometries of the constitutent layers. One can view the coordinate information in these PDFs by opening them in a software such as Adobe Acrobat and using the 'Tools> Measure> Geospatial Location Tool' option. This is also one way of verifying if the PDF is a geospatial PDF. This ability of the file format -to retain spatial info- allows extraction of the constituent layers back from the PDFs for any further analysis. However, such an extraction process is still not ideal since the attribute information, such as labels/names of the features, are still difficult to extract. And one also has to deal with projection/coordinate system related discrepancies that arise as a result of such extraction.

Till departments start sharing spatial data in usable formats, these workarounds should be of some help.
