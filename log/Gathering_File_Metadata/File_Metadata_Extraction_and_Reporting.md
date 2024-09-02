# File Metadata Extraction and Reporting

In this chapter, we explore essential techniques for analyzing and managing file systems using Python. We start with functions that provide valuable insights into file characteristics, including size distribution, type categorization, and age analysis. These tools are crucial for organizing and understanding large datasets, helping users make informed decisions about file management and archival.

The chapter demonstrates practical applications through various examples, such as calculating the distribution of file sizes across predefined bins, summarizing file types and their sizes, and analyzing file ages to identify how long files have been in the system. Additionally, it covers detailed file information retrieval, including size, creation and modification dates, and directory paths. These techniques are designed to streamline file handling processes, making it easier to manage and interpret file system data effectively.

## 1. File Size Distribution Analysis

Analyze the distribution of file sizes in a directory to identify large files or categorize them into size ranges.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/Gathering_File_Metadata/Example-01.png?raw=true)


```python
# import requird libraries
import os
import pandas as pd
from glob import glob

def file_size_distribution(path):
    file_list = glob(f'{path}/*.*')
    sizes = [os.path.getsize(file) / 1024 for file in file_list]  # Size in KB
    
    # Define size bins
    bins = [0, 100, 500, 1000, 5000, float('inf')]
    labels = ['0 - 100 KB', '101 - 500 KB', '501 - 1000 KB', '1001 - 5000 KB', '5001 KB and above']
    
    df = pd.DataFrame({'Size (KB)': sizes})
    df['Size Range'] = pd.cut(df['Size (KB)'], bins=bins, labels=labels, right=False)
    
    size_summary = df.groupby('Size Range').agg(
        Number_of_Files=('Size (KB)', 'count'),
        Total_Size_KB=('Size (KB)', 'sum')
    ).reset_index()
    
    return size_summary

# Example usage
df0= file_size_distribution('D:/Copy/Umer_Saeed')
df0
```

## 2. File Type Summary Report

Summarize the types of files in a directory, including counts and sizes for each file type.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/Gathering_File_Metadata/Example-02.png?raw=true)

```python
# import requird libraries
import os
import pandas as pd
from glob import glob

def file_type_summary(path):
    file_list = glob(f'{path}/*.*')
    extensions = [os.path.splitext(file)[1].lower() for file in file_list]
    sizes = [os.path.getsize(file) / 1024 for file in file_list]  # Size in KB
    
    df = pd.DataFrame({'Extension': extensions, 'Size (KB)': sizes})
    type_summary = df.groupby('Extension').agg(
        Number_of_Files=('Size (KB)', 'count'),
        Total_Size_KB=('Size (KB)', 'sum')
    ).reset_index()
    
    return type_summary

# Example usage
df0= file_type_summary('D:/Copy/Umer_Saeed')
df0
```

## 3. File Age Analysis

Determine the age of files based on their creation or last modification dates to identify old or unused files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/Gathering_File_Metadata/Example-03.png?raw=true)

```python
# import requird libraries
import os
import pandas as pd
from glob import glob
from datetime import datetime

def file_age_analysis(path):
    file_list = glob(f'{path}/*.*')
    creation_dates = [os.path.getctime(file) for file in file_list]
    current_time = datetime.now().timestamp()
    
    ages = [(current_time - creation) / (60 * 60 * 24 * 365) for creation in creation_dates]  # Age in years
    
    df = pd.DataFrame({'Age (Years)': ages})
    age_bins = [0, 1, 5, float('inf')]
    age_labels = ['Less than 1 year', '1 to 5 years', 'More than 5 years']
    
    df['Age Category'] = pd.cut(df['Age (Years)'], bins=age_bins, labels=age_labels, right=False)
    
    age_summary = df.groupby('Age Category').agg(
        Number_of_Files=('Age (Years)', 'count'),
        Total_Size_KB=('Age (Years)', 'size')  # Count as proxy for size in this example
    ).reset_index()
    
    return age_summary

# Example usage
df0 = file_age_analysis('D:/Copy/Umer_Saeed')
df0
```

## 4. Retrieve and Display File Metadata Including Name, Size, Creation Date, Modification Date, Extension, and Directory Path

The goal of this code is to gather and present detailed information about the files in a specific folder. It provides a list showing each file's name (without the extension), size, when it was created, when it was last modified, its type, and the folder it is located in.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/Gathering_File_Metadata/Example-04.png?raw=true)

```python
# import required libraries
import os
import math
import pandas as pd
from glob import glob

# user define funcation
def get_file_info(path):
    # Get the list of files
    file_list = glob(f'{path}/**/*.*',recursive=True)

    # Using list comprehension to collect file details
    file_info = [(os.path.splitext(os.path.basename(file_path))[0],  # File name without extension
                  math.ceil(os.path.getsize(file_path) / 1024),  # File size in KB, rounded up
                  pd.to_datetime(os.path.getctime(file_path), unit='s')  # File creation time in UTC
                  .tz_localize('UTC')  # Localize to UTC
                  .tz_convert('Asia/Karachi')  # Convert to your local timezone
                  .strftime('%Y-%m-%d %I:%M %p'),  # Format as date and time
                  pd.to_datetime(os.path.getmtime(file_path), unit='s')  # Last modification time in UTC
                  .tz_localize('UTC')  # Localize to UTC
                  .tz_convert('Asia/Karachi')  # Convert to your local timezone
                  .strftime('%Y-%m-%d %I:%M %p'),  # Format as date and time
                  os.path.splitext(file_path)[1].lower(),  # File extension
                  os.path.dirname(file_path)  # Directory path without file name and extension
                 )
                 for file_path in file_list]

    # Create a DataFrame
    df = pd.DataFrame(file_info, columns=['File Name', 'File Size (KB)',
                                          'Created Date', 'Modified Date',
                                          'File Extension', 'Full File Path'])
    return df

# Get file information from the source and destination directories
df0 = get_file_info('D:/Copy/Umer_Saeed')

# Display the DataFrame
df0
```


```python

```
