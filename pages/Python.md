- #Python
  collapsed:: false
	- Libraries
		- [[Pandas]]
		- [[arcpy]]
	- [[Workflow]]
-
- Examples:
	- Formatting for Specific Decimal Places
		-
		  ```python
		  float_format="{:0<4}".format #formats the decimals to "0.00"
		  float_format="{:0<5}".format #formats the decimals to "0.000"
		  float_format="{:0<7}".format #formats the decimals to "0.00000"
		  
		  ```
	- To time how fast your function or calculation takes use (timeit):
	  ```python
	  %timeit -n1000 -r1 random_prime(9900, 10000)
	  ```
		- Call timeit
			- Specify number of loops `-n1000` = 1000 loops
			- Use "best of" `-rn (n = # of runs)` function within `timeit` to see the slowest run, best run, and whether the result is being cached or not
	- Functools lru_cache which improves run time of code
		- To Import
		  ```python
		  from backports.functools_lru_cache import lru_cache
		  ```
		- Add the decorator lru_cache above function that you want to be enhanced 
		  ```python
		  @lru_cache(maxsize=None)
		  def func()
		  ```
		- If having an issue importing
			- Go to settings.json and add `"alias python": "python3"` after