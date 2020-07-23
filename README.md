# ESRI_GIS_PythonScript

While working for Applied Weather Associates, I used ESRI GIS technology and wrote a Python Script using ArcPython.  This was done to find the maximum climatological dew point
for a specific month in a specific area.  

In the example below, I wrote out a test for the month of June to retieive dew points in raster data format. 

try:
	import arcpy
	RasterLayer = "full_06_01"
	RasterLat = "40.24"
	RasterLon = "-86.94"
	RasterLonLat = RasterLon + " " + RasterLat
	arcpy.env.workspace = "C:\Users\pmangione\Documents\GIS Data\dew-point-GIS-data\Raster"
	result = arcpy.GetCellValue_management(RasterLayer, RasterLonLat)
	cellSize = result.getOutput(0)
	cellSize = str(cellSize)
	newList = cellSize
	newList = float(newList)
	print newList
	arcpy.AddMessage("The dewpoint value is " + str(newList))
	print arcpy.GetMessages()
except:
	print "Get Cell Value example failed."
	print arcpy.GetMessages()
