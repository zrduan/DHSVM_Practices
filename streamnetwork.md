***
The module consists of the following scripts and functions:

`createstreamnetwork.py ` - main script for the module, edits and settings are here.  
`channelclass.py` - function for channel classification.  
`soildepthscript.py` - function for generating soil depth raster.  
`wshdslope.py` - function for watershed slope.  
`roadaspect.py`  
`rowcolmap.py`  
`streammapfile.py`

### FAQs

* **Do I need to run every script in the module?**  
  No. You only need to run the main script `createstreamnetwork.py`.  

* **What are the edits/changes needed before running the module?**  
  Change the inputs in the "WorkSpace" and "Setup Input" section in `createstreamnetwork.py`.
  Modify the channel classification criteria in `channelclass.py` based on local topo and channel characteristics.
  You're also recommend to modify the threshold values in `soildepthscript.py`.

* **What if I encounter error message when running the scripts?**  
  If it's an error message from the script, read the message and follow the instruction of the message. 
  If it's an error message with an error code, search ArcGIS with the error code and follow the explanations. 

* **"Memory Error"**

  There're two types of memory error:

  1. At the beginning of the run:

     Open ArcMap, click on "Customize - ArcMap Options" on toolbar. Under "Raster" tab, change "Maximum number of unique values to render" to a reasonable larger value. 

  2. When running on "rowcolmap" function: 

     For large domains (generally larger than 2000*3000 grids), the rowcolmap function may fail due to limitation on ArcGIS memory usage. One solution is to release some memory by deleting some unnecessary variables. Then run rowcolmap function line by line. Another solution is to generate a rowcolpoly shapefile in ArcMap. I'll also work on updating the function to make it more friendly to large domains.   


***




