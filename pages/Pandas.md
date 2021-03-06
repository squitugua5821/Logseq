- Example(s):
  collapsed:: false
	- Read in `.CSV`
		-
		  ```python
		  import pandas as pd
		  
		  df = pd.read_csv('.csv', header = 1) #import .csv into dataframe and remove top row
		  df = pd.read_excel('.csv', header = 1) #import .xlsx
		  df = pd.ExcelFile('.csv', header = 1) #import .xlsx
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
	- Find first and second Elements within a dict and save into separate variables
		-
		  ```python
		  sheet1, sheet2 = tabs[0], tabs[1]
		  ```
			- Manipulate the filename provided by user with string saved in previous code block
				- Original Filename: ```P2006650 & P2006660_2_WR AP Sum AP Det NOD23 for May 20-21 as of 2021.06.04```
			-
			  ```python
			  filenamer = sheet1[6:] + user_filename[17:-5] + '.csv'
			  ```
				- This removes everything from the 6th position onward to remove the 'NOD23 ' in front of the intended string then added to the original filename starting from the 17th position and ending at -5
	- Remove columns that are empty (pandas names them "Unnamed: x")
		-
		  ```python
		  df = df[df.columns.drop(list(df.filter(regex='Unnamed:')))]
		  ```
- Links:
  collapsed:: false
	- [to_frame(), to_list(), astype(), get_dummies() and map()](https://machinelearningknowledge.ai/pandas-tutorial-to_frame-to_list-astype-get_dummies-and-map/#:~:text=Syntax%201%20data%20%3A%20array-like%2C%20Series%2C%20or%20DataFrame,used%20for%20considering%20null%20values.%20More%20items...%20)
	- [Official Pandas Documentation](https://pandas.pydata.org/docs/)
	- [Tutorial (Awesome)](https://calmcode.io/)
	- [Pandas Pipe](https://calmcode.io/pandas-pipe/introduction.html)