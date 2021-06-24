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
			- Go to settings.json and add `"alias python": "python3"` after `"source": "Git Bash"` looks like this:
			  ```        "Git Bash": {
			              "source": "Git Bash",
			              "alias python": "python3"
			          }
			      }
			  }```
				- This problem occurs with Python 2.7 usually
	- Creating an app
		- Use Poetry #Workflow to organize everything
		- Create a src folder and module folder (where all of the functions live) then create a folder for main app.py
		- Import the modules and then to call the funcs within the module, use the func name `.func` looks like this:
		  ```python
		  
		  ``` from cycle_a import (
		    agent_of_record,
		    back_out,
		    bill_reg,
		    boa_flow,
		    cash_application,
		    credit_invoices,
		    dept_of_insurance,
		    nod23,
		    sco_dex_flow,
		  ) 
		  def main():
		    """Dictionary provides the options to select via CLI, will be removed and functions inserted
		    once this is ready to be automated
		    """ 
		  while True: 
		  try:
		            print(
		                "\n         *****Main Menu*****",
		                "\n=====================================\nTo Terminate Program Press 'Ctrl   C'\n=====================================",
		            )
		            func_dict = {
		                "1": bill_reg.bill_Register,
		                "2": back_out.backed_Out,
		                "3": boa_flow.boa,
		                "4": cash_application.cash_app,
		                "5": agent_of_record.agent_record,
		                "6": dept_of_insurance.doi,
		                "7": sco_dex_flow.sco_dex,
		                "8": credit_invoices.credit_invoice,
		                "9": nod23.nod_23,
		-