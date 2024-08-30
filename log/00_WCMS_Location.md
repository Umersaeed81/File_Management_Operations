#  [Umer Saeed](https://www.linkedin.com/in/engumersaeed/)
Sr. RF Planning & Optimization Engineer<br>
BSc Telecommunications Engineering, School of Engineering<br>
MS Data Science, School of Business and Economics<br>
**University of Management & Technology**<br>

# User Address Extraction in WCMS Complaints
![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/WCMS_Title.png?raw=true)

## Task Description

PTML has provided the WCMS complaints data in an Excel file for analysis. The objective of this Python script is to extract the 'User Address' information from the 'Standard Comments' column.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/WCMS_Task_Description.png?raw=true)

## Import Required Libraries

The code imports the os and pandas libraries and configures the environment to suppress warning messages. This setup ensures a clean and uninterrupted execution for the upcoming data processing tasks.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/WCMS_Import_Libraries.png?raw=true)


```python
import os
import pandas as pd
import warnings
warnings.simplefilter("ignore")
```

## Set Input File Path

The code sets the input path to `'D:/Advance_Data_Sets/WCMS'` and changes the current working directory to this specified path. This ensures that subsequent file operations are performed in the correct directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/WCML_Filt_Path.png?raw=true)


```python
# Set the Input Path 
path = 'D:/Advance_Data_Sets/WCMS'
os.chdir(path)
```

## Import Input File

The code reads data from an Excel file named `'WCMS.xlsx'` into a pandas DataFrame. It specifies that the second row of the file should be used as the header and selects only the columns `'MSISDN'`, `'Complaint Id'`, `'Region'`, and `'Standard Comments'` for inclusion in the DataFrame.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/WCMS_Import_Data_Set.png?raw=true)


```python
df = pd.read_excel('WCMS.xlsx',\
                   header=1,\
                   usecols=['MSISDN','Complaint Id','Region','Standard Comments'])
```

## Code for Extracting and Filtering Location Information from Complaint Data

The code performs the following steps:

**1. Convert 'Standard Comments' Column to List:** Splits the entries in the `'Standard Comments'` column by the '|' character and converts them into lists.

**2. Filter 'Party A' Elements:** Filters out the comments that contain 'Party A' from each list and creates a new column `'Filtered Comments'` with these filtered comments.


**3. Extract Location Information:** Extracts the location from the filtered comments. It splits each comment by the ';' character and retrieves the second part (if available), storing it in a new column `'Location'`.


**4. Filter Required Columns:** Selects only the relevant columns (`'MSISDN'`, `'Complaint Id'`, `'Region'`, and `'Location'`) and stores the result in a new DataFrame `df1`.


**5. Export Output:** Saves the filtered DataFrame `df1` to a CSV file named `'Location.csv'`, excluding the index column.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/Data_Processing.png?raw=true)


```python
# Convert 'Standard Comments' Column to list
df.loc[:, 'Standard Comments']  = df['Standard Comments'].str.split('|').apply(list)
```


```python
# Filter Party A Element From the list
df['Filtered Comments'] = df['Standard Comments'].\
                          apply(lambda comments: [comment for comment in comments if 'Party A' in comment])
```


```python
# Extract only the Location
df['Location'] = df['Filtered Comments'].apply(lambda comments: comments[0].split(';')[1] if comments else None)
```


```python
# Filter Required Columns
df1 = df[['MSISDN','Complaint Id','Region','Location']]
```


```python
# Export Output File
df1.to_csv('Locaton.csv',index=False)
```
