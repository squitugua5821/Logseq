- When creating a script that will iterate through a for loop to create feature layers for ArcMap
	- Allow the files to be overwritten otherwise the files will not save for the existing list that you create
	-
	  ```python
	  arcpy.env.overwriteOutput = True
	  ```
	- Variables: Create variables to hold raw directories for .shp (dataset that you are working with)
	  ```python
	  points = r'H:\ArcMAP_Prac\populated_data\ne_10m_populated_places.shp'
	  countries = r'H:\ArcMAP_Prac\populated_data\ne_10m_admin_0_countries.shp'
	  outpath = r'H:\ArcMAP_Prac\output'
	  ```
	- Make Feature Layers and iterate through a given list
	  
	  ```python 
	  countries_of_interest = ['United States', 'Italy', 'Kenya', 'Gambia', 'Jordan', 'Lebanon', 'France']
	  arcpy.MakeFeatureLayer_management(points, 'points_layer') for country in countries_of_interest:
	    print(country)
	    arcpy.MakeFeatureLayer_management(countries, 'countries_layer',""" "NAME" = '{}' """.format(country)) arcpy.SelectLayerByLocation_management('points_layer', 'WITHIN', 'countries_layer')
	    arcpy.FeatureClassToFeatureClass_conversion('points_layer', outpath, 'cities_in_{}'.format(country)) 
	  ```
	- The files will go to the location that you provided then Drag and Drop the `.shp` to ArcMap
		- Make sure that the names you are referring to match what is in the Table Attributes