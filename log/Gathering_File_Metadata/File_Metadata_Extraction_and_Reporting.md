<table style="border-collapse: collapse;">
  <tr>
    <td style="vertical-align: top;">
      <h1><a href="https://www.linkedin.com/in/engumersaeed/">Umer Saeed</a></h1>
      Sr. RF Planning & Optimization Engineer<br>
      BSc Telecommunications Engineering, School of Engineering<br>
      MS Data Science, School of Business and Economics<br>
      <strong>University of Management & Technology</strong><br>
      <strong>Mobile:</strong> +923018412180<br>
      <strong>Email:</strong> umersaeed81@hotmail.com<br>
      <strong>Address:</strong> Dream Gardens, Defence Road, Lahore<br>
    </td>
    <td style="vertical-align: top; padding-left: 100px;">
      <img src="https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true" alt="Bano Qabil Logo" width="500"/>
    </td>
  </tr>
</table>

# File Metadata Extraction and Reporting
![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/Gathering_File_Metadata/File_Metadata_Extraction_and_Reporting.png?raw=true)


In the realm of data management, understanding and analyzing file metadata is crucial for effective file system management and optimization. As datasets and file systems grow in complexity, the ability to extract, analyze, and report on file metadata becomes increasingly important. This chapter delves into essential techniques for gathering and interpreting file metadata using Python, providing valuable insights into various aspects of file characteristics and system organization.

The chapter begins by exploring fundamental functions that allow users to extract critical information about files, such as their sizes, types, and ages. These functions serve as the foundation for analyzing large datasets, enabling users to categorize files, assess their distribution, and make informed decisions about file management and archival strategies. By leveraging these techniques, you can gain a deeper understanding of your file system's structure and content.

One of the primary techniques covered is **size distribution analysis**, where we demonstrate how to calculate and visualize the distribution of file sizes across predefined bins. This approach helps in identifying patterns in file sizes, managing disk space more effectively, and making strategic decisions about file storage and cleanup.

Next, we address **type categorization**, where we summarize the types of files present in the system and their corresponding sizes. This technique is particularly useful for organizing files based on their formats, facilitating easier management and retrieval. By categorizing files into groups, you can streamline data processing tasks and ensure that files are handled according to their specific types.

**File age analysis** is another key aspect of this chapter. We explore methods for determining how long files have been in the system by examining their creation and modification dates. This analysis is valuable for identifying old or outdated files that may need to be archived or deleted, helping to maintain an efficient and relevant file system.

In addition to these analyses, the chapter covers detailed file information retrieval. We provide examples of how to access and report on essential file attributes, including size, creation and modification dates, and directory paths. This comprehensive approach to metadata extraction ensures that you can manage and interpret file system data with precision and clarity.

By mastering these techniques, you will be equipped to handle file metadata extraction and reporting effectively. Whether for organizing large datasets, optimizing storage, or making strategic decisions about file management, these tools and methods will enhance your ability to manage and interpret file system data, contributing to a more organized and efficient digital environment.

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

# Display the result
df0
```


### Output

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Size Range</th>
      <th>Number_of_Files</th>
      <th>Total_Size_KB</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0 - 100 KB</td>
      <td>15</td>
      <td>285.271484</td>
    </tr>
    <tr>
      <th>1</th>
      <td>101 - 500 KB</td>
      <td>0</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>501 - 1000 KB</td>
      <td>0</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1001 - 5000 KB</td>
      <td>3</td>
      <td>7935.145508</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5001 KB and above</td>
      <td>0</td>
      <td>0.000000</td>
    </tr>
  </tbody>
</table>
</div>



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

# Display the result
df0
```
### Output

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Extension</th>
      <th>Number_of_Files</th>
      <th>Total_Size_KB</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>.csv</td>
      <td>2</td>
      <td>3734.724609</td>
    </tr>
    <tr>
      <th>1</th>
      <td>.docx</td>
      <td>1</td>
      <td>45.729492</td>
    </tr>
    <tr>
      <th>2</th>
      <td>.txt</td>
      <td>6</td>
      <td>0.015625</td>
    </tr>
    <tr>
      <th>3</th>
      <td>.xlsx</td>
      <td>9</td>
      <td>4439.947266</td>
    </tr>
  </tbody>
</table>
</div>



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

# Display the result
df0
```
### Output

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age Category</th>
      <th>Number_of_Files</th>
      <th>Total_Size_KB</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Less than 1 year</td>
      <td>18</td>
      <td>18</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1 to 5 years</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>More than 5 years</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>



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

# Display the result
df0
```
### Output




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>File Name</th>
      <th>File Size (KB)</th>
      <th>Created Date</th>
      <th>Modified Date</th>
      <th>File Extension</th>
      <th>Full File Path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>03_PRS</td>
      <td>1868</td>
      <td>2024-06-12 06:36 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1234_US_G</td>
      <td>0</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>2</th>
      <td>15031984_AliSaeed</td>
      <td>0</td>
      <td>2024-09-01 02:31 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>3</th>
      <td>19980802_UmerSaeed</td>
      <td>30</td>
      <td>2024-09-01 02:32 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AS_123_US</td>
      <td>30</td>
      <td>2024-06-13 05:46 PM</td>
      <td>2024-06-13 05:46 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Babar_Azam</td>
      <td>30</td>
      <td>2024-09-01 02:19 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Cor_US</td>
      <td>46</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>7</th>
      <td>gmail</td>
      <td>0</td>
      <td>2024-06-13 05:24 AM</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>8</th>
      <td>g_AS</td>
      <td>0</td>
      <td>2024-06-13 05:18 AM</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>9</th>
      <td>g_US</td>
      <td>30</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:01 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Hello_US</td>
      <td>1868</td>
      <td>2024-06-13 04:55 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Ijlal_Khan</td>
      <td>30</td>
      <td>2024-09-01 02:17 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Pakistan_1947-08-14</td>
      <td>0</td>
      <td>2024-09-01 02:30 PM</td>
      <td>2024-09-01 02:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Test</td>
      <td>30</td>
      <td>2024-06-22 11:30 PM</td>
      <td>2024-06-18 10:38 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Test1</td>
      <td>31</td>
      <td>2024-08-13 06:37 PM</td>
      <td>2024-08-11 10:53 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>15</th>
      <td>US1234</td>
      <td>1</td>
      <td>2024-06-13 04:46 PM</td>
      <td>2024-09-01 02:24 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>16</th>
      <td>US_123_AS</td>
      <td>30</td>
      <td>2024-06-13 05:46 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>17</th>
      <td>US_Test</td>
      <td>4201</td>
      <td>2024-06-13 05:53 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>18</th>
      <td>g</td>
      <td>0</td>
      <td>2024-08-13 07:30 PM</td>
      <td>2024-08-13 07:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\BH</td>
    </tr>
    <tr>
      <th>19</th>
      <td>a</td>
      <td>1868</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>20</th>
      <td>AS_1234_US</td>
      <td>30</td>
      <td>2024-08-11 03:54 PM</td>
      <td>2024-08-11 03:54 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>21</th>
      <td>b</td>
      <td>1</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-06-12 06:36 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>22</th>
      <td>c</td>
      <td>30</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-06-12 06:35 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>23</th>
      <td>d</td>
      <td>1868</td>
      <td>2024-08-11 11:43 AM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Hello_t_US</td>
      <td>1868</td>
      <td>2024-08-11 03:32 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>25</th>
      <td>US1234_Salam</td>
      <td>0</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-13 04:46 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>26</th>
      <td>US_123_AS_Hello</td>
      <td>30</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>27</th>
      <td>US_Test_Hi</td>
      <td>4201</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>28</th>
      <td>1234_US_G</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>29</th>
      <td>15031984_AliSaeed</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>30</th>
      <td>19980802_UmerSaeed</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Babar_Azam</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Cor_US</td>
      <td>46</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>33</th>
      <td>gmail</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>34</th>
      <td>g_AS</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Ijlal_Khan</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Pakistan_1947-08-14</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>37</th>
      <td>US1234</td>
      <td>1</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:24 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>38</th>
      <td>US_123_AS</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>39</th>
      <td>US_Test</td>
      <td>4201</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
  </tbody>
</table>
</div>

## 5. Extracting and Analyzing File Information from a Directory

The objective of this code is to collect and present comprehensive details about the files within a specified directory. It generates a list that includes each file's name (excluding the extension), size, creation date, last modification date, file type, and its directory path. Additionally, the code retrieves and displays the author name for each file, where available.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/Gathering_File_Metadata/Example-05.png?raw=true)

```python
# import required libraries
import os
import math
import pandas as pd
from glob import glob
from docx import Document
from openpyxl import load_workbook
from PyPDF2 import PdfFileReader

# pip install python-docx openpyxl PyPDF2

# Function to extract the author name from specific file types
def extract_author(file_path):
    try:
        ext = os.path.splitext(file_path)[1].lower()
        if ext == '.docx':  # Microsoft Word documents
            doc = Document(file_path)
            return doc.core_properties.author
        elif ext == '.xlsx':  # Microsoft Excel files
            wb = load_workbook(file_path, read_only=True)
            return wb.properties.creator
        elif ext == '.pdf':  # PDF documents
            with open(file_path, 'rb') as f:
                reader = PdfFileReader(f)
                info = reader.getDocumentInfo()
                return info.author if info else None
        # Add more conditions for other file types if needed
    except Exception as e:
        return None  # If there's an error or no author info, return None

# User-defined function to get file info
def get_file_info(path):
    # Get the list of files
    file_list = glob(f'{path}/**/*.*', recursive=True)

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
                  os.path.dirname(file_path),  # Directory path without file name and extension
                  extract_author(file_path)  # Extract author name if available
                 )
                 for file_path in file_list]

    # Create a DataFrame
    df = pd.DataFrame(file_info, columns=['File Name', 'File Size (KB)',
                                          'Created Date', 'Modified Date',
                                          'File Extension', 'Full File Path', 'Author Name'])
    return df

# Get file information from the source and destination directories
df0 = get_file_info('D:/Copy/Umer_Saeed')

# Display the result
df0
```
### Output

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>File Name</th>
      <th>File Size (KB)</th>
      <th>Created Date</th>
      <th>Modified Date</th>
      <th>File Extension</th>
      <th>Full File Path</th>
      <th>Author Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>03_PRS</td>
      <td>1868</td>
      <td>2024-06-12 06:36 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>None</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1234_US_G</td>
      <td>0</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>None</td>
    </tr>
    <tr>
      <th>2</th>
      <td>15031984_AliSaeed</td>
      <td>0</td>
      <td>2024-09-01 02:31 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>None</td>
    </tr>
    <tr>
      <th>3</th>
      <td>19980802_UmerSaeed</td>
      <td>30</td>
      <td>2024-09-01 02:32 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AS_123_US</td>
      <td>30</td>
      <td>2024-06-13 05:46 PM</td>
      <td>2024-06-13 05:46 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Babar_Azam</td>
      <td>30</td>
      <td>2024-09-01 02:19 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Cor_US</td>
      <td>46</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>7</th>
      <td>gmail</td>
      <td>0</td>
      <td>2024-06-13 05:24 AM</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>None</td>
    </tr>
    <tr>
      <th>8</th>
      <td>g_AS</td>
      <td>0</td>
      <td>2024-06-13 05:18 AM</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>None</td>
    </tr>
    <tr>
      <th>9</th>
      <td>g_US</td>
      <td>30</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:01 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Hello_US</td>
      <td>1868</td>
      <td>2024-06-13 04:55 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>None</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Ijlal_Khan</td>
      <td>30</td>
      <td>2024-09-01 02:17 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Pakistan_1947-08-14</td>
      <td>0</td>
      <td>2024-09-01 02:30 PM</td>
      <td>2024-09-01 02:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>None</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Test</td>
      <td>30</td>
      <td>2024-06-22 11:30 PM</td>
      <td>2024-06-18 10:38 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Test1</td>
      <td>31</td>
      <td>2024-08-13 06:37 PM</td>
      <td>2024-08-11 10:53 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>15</th>
      <td>US1234</td>
      <td>1</td>
      <td>2024-06-13 04:46 PM</td>
      <td>2024-09-01 02:24 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>None</td>
    </tr>
    <tr>
      <th>16</th>
      <td>US_123_AS</td>
      <td>30</td>
      <td>2024-06-13 05:46 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>17</th>
      <td>US_Test</td>
      <td>4201</td>
      <td>2024-06-13 05:53 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>18</th>
      <td>g</td>
      <td>0</td>
      <td>2024-08-13 07:30 PM</td>
      <td>2024-08-13 07:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\BH</td>
      <td>None</td>
    </tr>
    <tr>
      <th>19</th>
      <td>a</td>
      <td>1868</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>None</td>
    </tr>
    <tr>
      <th>20</th>
      <td>AS_1234_US</td>
      <td>30</td>
      <td>2024-08-11 03:54 PM</td>
      <td>2024-08-11 03:54 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>21</th>
      <td>b</td>
      <td>1</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-06-12 06:36 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>None</td>
    </tr>
    <tr>
      <th>22</th>
      <td>c</td>
      <td>30</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-06-12 06:35 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>23</th>
      <td>d</td>
      <td>1868</td>
      <td>2024-08-11 11:43 AM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>None</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Hello_t_US</td>
      <td>1868</td>
      <td>2024-08-11 03:32 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>None</td>
    </tr>
    <tr>
      <th>25</th>
      <td>US1234_Salam</td>
      <td>0</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-13 04:46 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>None</td>
    </tr>
    <tr>
      <th>26</th>
      <td>US_123_AS_Hello</td>
      <td>30</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>27</th>
      <td>US_Test_Hi</td>
      <td>4201</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>28</th>
      <td>1234_US_G</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>None</td>
    </tr>
    <tr>
      <th>29</th>
      <td>15031984_AliSaeed</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>None</td>
    </tr>
    <tr>
      <th>30</th>
      <td>19980802_UmerSaeed</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Babar_Azam</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Cor_US</td>
      <td>46</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>33</th>
      <td>gmail</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>None</td>
    </tr>
    <tr>
      <th>34</th>
      <td>g_AS</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>None</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Ijlal_Khan</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Pakistan_1947-08-14</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>None</td>
    </tr>
    <tr>
      <th>37</th>
      <td>US1234</td>
      <td>1</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:24 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>None</td>
    </tr>
    <tr>
      <th>38</th>
      <td>US_123_AS</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>Umer Saeed</td>
    </tr>
    <tr>
      <th>39</th>
      <td>US_Test</td>
      <td>4201</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
      <td>Umer Saeed</td>
    </tr>
  </tbody>
</table>
</div>


## 6. Duplicate File Finder

The objective of this code is to identify and group duplicate files within a specified directory based on their content. The script calculates a unique hash value for each file using the MD5 hashing algorithm. If two or more files have the same hash, they are considered duplicates and are grouped together. Files that do not have a matching hash with any other file are not considered duplicates and are excluded from the results. The program then outputs the duplicate groups, listing the file paths for each group. This is useful for cleaning up storage space, organizing files, and ensuring that only unique files are retained in a directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/Gathering_File_Metadata/Example-06.png?raw=true)

```python
# import required libraries
import os
import hashlib
import pandas as pd
from glob import glob

def find_duplicates(path):
    file_list = glob(f'{path}/*.*')
    file_hashes = {}
    
    for file_path in file_list:
        with open(file_path, 'rb') as f:
            file_hash = hashlib.md5(f.read()).hexdigest()
            if file_hash in file_hashes:
                file_hashes[file_hash].append(file_path)
            else:
                file_hashes[file_hash] = [file_path]
    
    duplicate_groups = {k: v for k, v in file_hashes.items() if len(v) > 1}
    
    for group, files in duplicate_groups.items():
        print(f"Duplicate Group: {group}")
        for file in files:
            print(f"  {file}")
        print()

# Example usage
find_duplicates('D:/Copy/Umer_Saeed')
```

### Output
```python
  Duplicate Group: 1e0009d787ddc52a793c2073e373a89f
    D:/Copy/Umer_Saeed\03_PRS.csv
    D:/Copy/Umer_Saeed\Hello_US.csv
  
  Duplicate Group: d41d8cd98f00b204e9800998ecf8427e
    D:/Copy/Umer_Saeed\1234_US_G.txt
    D:/Copy/Umer_Saeed\15031984_AliSaeed.txt
    D:/Copy/Umer_Saeed\gmail.txt
    D:/Copy/Umer_Saeed\g_AS.txt
    D:/Copy/Umer_Saeed\Pakistan_1947-08-14.txt
```

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true)

