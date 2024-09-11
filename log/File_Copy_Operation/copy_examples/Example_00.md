
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

# Copying a File to a Target Folder with Pre-Check Validations Using `shutil.copy()`

# Example-1

The purpose of this code is to copy a single file (in this case, **Test.xlsx**) to a target folder. The code performs the following checks and actions:
- It verifies that there is enough free space in the target directory before proceeding with the copy operation.
- If the source directory does not exist, an error message is displayed.
- If the source file is not found, an error message is displayed.
- If the target folder does not exist, it is created before copying the file.
- Note that if a file with the same name already exists in the target folder, it will be overwritten.
- The code uses **shutil.copy()**, which results in the file's metadata being updated to reflect the current time of the copy operation. Consequently, the last modification time will show the current time rather than the original file's modification time.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Copy_Operation/copy_example_fig/Example-00.png?raw=true)

## Importing Required Modules


```python
import os
import math
import shutil
import pandas as pd
from glob import glob
```

## Setting Source File and Destination Folder Paths


```python
# Define the source and destination directory paths
file_path = "D:/Copy/Umer_Saeed/Test.xlsx"
destination_folder = 'D:/Copy/Ali_Saeed/'
```

## Function to Get Free Disk Space


```python
def get_free_space(directory):
    # Get disk usage statistics for the specified directory
    usage = shutil.disk_usage(directory)
    # Extract the free space in bytes
    free_space = usage.free
    return free_space
```

## Checking and Copying the File to the Destination


```python
# Extract the directory from the file path
directory_path = os.path.dirname(file_path)

# Initialize a file copy counter
copy_counter = 0

# Check if the directory path exists
if os.path.exists(directory_path):
    # Check if the file exists
    if os.path.isfile(file_path):
        # Check if the destination folder exists, create it if not
        os.makedirs(destination_folder, exist_ok=True)
        # Get the size of the file in bytes
        total_size = os.path.getsize(file_path)
        # Get the correct drive of the destination folder
        destination_drive = os.path.splitdrive(destination_folder)[0]
        # Check if there is enough free space in the destination directory
        free_space = get_free_space(destination_drive)
        if free_space >= total_size:
            # Use shutil.copy() to copy the file to the destination folder
            shutil.copy(file_path, destination_folder)
            copy_counter += 1  # Increment the counter
            print(f"File Copied Successfully. Number of files copied: {copy_counter}")
        else:
            print("Error: Not Enough Free Space in the Destination Directory.")
    else:
        print("Error: Source File not Found.")
else:
    print("Error: Source Directory Path not Found.")
```

    File Copied Successfully. Number of files copied: 1
    

## Gathering and Formatting File Metadata


```python
def get_file_info(path):
    # Get the list of files
    file_list = glob(f'{path}/*.*')

    # Using list comprehension to collect file details
    file_info = [(os.path.basename(file_path),  # Extract the file name from the path
                  math.ceil(os.path.getsize(file_path) / 1024),  # File size in KB, rounded up
                  pd.to_datetime(os.path.getmtime(file_path), unit='s')  # Last modification time in UTC
                  .tz_localize('UTC')  # Localize to UTC
                  .tz_convert('Asia/Karachi')  # Convert to your local timezone
                  .strftime('%Y-%m-%d %I:%M %p'),  # Format as date and time
                  os.path.splitext(file_path)[1].lower(),  # File extension
                  file_path,  # Full file path
                 )
                 for file_path in file_list]

    # Create a DataFrame
    df = pd.DataFrame(file_info, columns=['File Name', 'File Size (KB)',
                                                    'Last Modification Time',
                                                    'File Extension', 'Full File Path'])
    return df


# Get file information from the source and destination directories
file_info_source_directory = get_file_info('D:/Copy/Umer_Saeed')
file_info_destination_folder = get_file_info('D:/Copy/Ali_Saeed')
```


```python
file_info_source_directory
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>File Name</th>
      <th>File Size (KB)</th>
      <th>Last Modification Time</th>
      <th>File Extension</th>
      <th>Full File Path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>03_PRS.csv</td>
      <td>1868</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\03_PRS.csv</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1234_US_G.txt</td>
      <td>0</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\1234_US_G.txt</td>
    </tr>
    <tr>
      <th>2</th>
      <td>15031984_AliSaeed.txt</td>
      <td>0</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\15031984_AliSaeed.txt</td>
    </tr>
    <tr>
      <th>3</th>
      <td>19980802_UmerSaeed.xlsx</td>
      <td>30</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\19980802_UmerSaeed.xlsx</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AS_123_US.xlsx</td>
      <td>30</td>
      <td>2024-06-13 05:46 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\AS_123_US.xlsx</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Babar_Azam.xlsx</td>
      <td>30</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Babar_Azam.xlsx</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Cor_US.docx</td>
      <td>46</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed\Cor_US.docx</td>
    </tr>
    <tr>
      <th>7</th>
      <td>gmail.txt</td>
      <td>0</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\gmail.txt</td>
    </tr>
    <tr>
      <th>8</th>
      <td>g_AS.txt</td>
      <td>0</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\g_AS.txt</td>
    </tr>
    <tr>
      <th>9</th>
      <td>g_US.xlsx</td>
      <td>30</td>
      <td>2024-06-13 05:01 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\g_US.xlsx</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Hello_US.csv</td>
      <td>1868</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\Hello_US.csv</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Ijlal_Khan.xlsx</td>
      <td>30</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Ijlal_Khan.xlsx</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Pakistan_1947-08-14.txt</td>
      <td>0</td>
      <td>2024-09-01 02:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Pakistan_1947-08-14.txt</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Test.xlsx</td>
      <td>30</td>
      <td>2024-06-18 10:38 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Test.xlsx</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Test1.xlsx</td>
      <td>31</td>
      <td>2024-08-11 10:53 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Test1.xlsx</td>
    </tr>
    <tr>
      <th>15</th>
      <td>US1234.txt</td>
      <td>1</td>
      <td>2024-09-01 02:24 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\US1234.txt</td>
    </tr>
    <tr>
      <th>16</th>
      <td>US_123_AS.xlsx</td>
      <td>30</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\US_123_AS.xlsx</td>
    </tr>
    <tr>
      <th>17</th>
      <td>US_Test.xlsx</td>
      <td>4201</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\US_Test.xlsx</td>
    </tr>
  </tbody>
</table>
</div>




```python
file_info_destination_folder
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>File Name</th>
      <th>File Size (KB)</th>
      <th>Last Modification Time</th>
      <th>File Extension</th>
      <th>Full File Path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Test.xlsx</td>
      <td>30</td>
      <td>2024-09-11 08:33 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed\Test.xlsx</td>
    </tr>
  </tbody>
</table>
</div>



## Export Source and Destination File Information


```python
# set path
folder_path = 'D:/copy_output'
os.chdir(folder_path)

# Write excel file with default behaviour.
with pd.ExcelWriter("00_Example.xlsx",date_format = 'dd-mm-yyyy',datetime_format='dd-mm-yyyy') as writer:
    # Export File Information
    file_info_source_directory.to_excel(writer, sheet_name='Source',index=False)
    file_info_destination_folder.to_excel(writer, sheet_name='Destination',index=False)
```

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true)