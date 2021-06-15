- Example(s):
	- Read in `.CSV`
		-
		  ```python
		  import pandas as pd
		  
		  df = pd.read_csv('.csv', header = 1) #import .csv into dataframe and remove top row
		  ```
	- Count Rows and Columns of DataFrame
		-
		  ```python
		  row_count = df.shape[0]
		  col_count = df.shape[1]
		  ```
	- Read tabs from `.XLSX` and save into variable (Output is a dictionary of tab names)
		-
		  ```python
		  user_read = user_path + user_filename
		  xlsx = pd.ExcelFile(user_read)
		  sheets = xlsx.sheet_names
		  ```
			- Look for specific tab within the dict of tabs and save into a separate variable
				-
				  ```python
				  tabs = []
				    for match in sheets:
				        if 'NOD23 P' in match:
				             tabs.append(match)
				  ```
			-