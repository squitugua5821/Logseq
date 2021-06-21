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