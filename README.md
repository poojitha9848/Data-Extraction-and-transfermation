# Data-Extraction-and-transfermation
#excel data filtering script
#over view
This script reads data from an excel file,filters specific columns,and write filtered data to a new excel file .It ensures that the required columns are present before performing filtering 
operation
#Prerequisites
-python 3.5
-'panadas' library
-An excel file named 'sample2.xlsx'.(or adjust the file name in the script as needed)
#Installation
1.Make sure you have python 3.5 installed.you can downloload it from [python.org](http://www.python.org/downloads).
2.install the required python library using pip:
''' bash
pip install pandas openpyxl
Note:'openpyxl'is needed for reading and writing excel files.
USAGE:
1.Place the excel file you want to process in the same directory as the script and name it 'sample2.xlsx'.you can adjust the file name in the script needed.
2.Run the script.The script will filtr the columns 'STUDENTNAME','PHNO',and 'EMAIL' from the input file.
3.The filtered data will be saved to a new excel file named 'pooji.xlsx'.
CODE EXPLANATION:
import pandas as pd
#input_file='sample2.xlsx'
#output_file='pooji.xlsx'
try:
#read the data  excel file
 data=pd.read_excel('sample2.xlsx')
 #filter specific columns
 column_to_filter=['STUDENTNAME','PHNO','EMAIL']
 if all(column in data.columns for column in column_to_filter):
    filtered_data=data[column_to_filter]
    if not filtered_data.empty:
       #write to another excel file
      filtered_data.to_excel('pooji.xlsx',index=False)
      print("successfully copy in 'pooji.xlsx'.")
    else:
       print("the filtered_data is not empty")
 else:
    print("all columns  is not present in pooji.xlsx ")
except FileNotFoundError:
    print(f"ERROR:The file was not found")
except KeyError as e:
    print(f"Error:{e}")
except Exception as e:
    print(f"unexpected error occured: {e}")
--------------------------------------------
ERROR HANDLING:
1.FileNotFoundError:Raised if the input file is not found
2.KeyError:Raised if the specified columns are not found in the found 
3.General 'Exception':Catches any other unexpected errors.
TROUBLESHOOTING:
1.ensure that input file 'sample2.xlsx' is in the same directory as the script or provide the correct path.
2.Verify that the columns 'STUDENTNAME','PHNO','EMAIL' exists in the input file.


