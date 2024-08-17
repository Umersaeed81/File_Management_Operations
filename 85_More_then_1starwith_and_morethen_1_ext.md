# Example-86


```python

```

## Importing Required Modules


```python
import os
import math
import shutil
import pandas as pd
from glob import glob
from itertools import product
```

## Setting Source File and Destination Folder Paths


```python
# Define the source and destination directory paths
source_directory = 'D:/Copy/Umer_Saeed/'
destination_folder = 'D:/Copy/Ali_Saeed/'
```

## Function to Get Free Disk Space


```python
# Function to get free space on the disk
def get_free_space(directory):
    usage = shutil.disk_usage(directory)
    free_space = usage.free
    return free_space
```

## Function to Generate a Unique Filename in the Destination Directory


```python
# Function to generate unique filename
def generate_unique_filename(source_file, destination_directory):
    base_filename, file_extension = os.path.splitext(os.path.basename(source_file))
    destination_file_path = os.path.join(destination_directory, os.path.basename(source_file))
    counter = 1
    while os.path.exists(destination_file_path):
        new_filename = f"{base_filename}_{counter}{file_extension}"
        destination_file_path = os.path.join(destination_directory, new_filename)
        counter += 1
    return destination_file_path
```

## Checking and Copying the File to the Destination


```python
# Check if the source directory exists
if not os.path.exists(source_directory):
    print(f"Error: Source directory '{source_directory}' not found.")
else:
    # Define the base patterns and extensions
    base_patterns = ['AS*', 'US*']
    extensions = ['.xlsx', '.txt']
    # Generate all combinations of base patterns with extensions
    patterns = list(product(base_patterns, extensions))
    # Construct the file paths
    file_paths = [file
              for base_pattern, extension in patterns
              for file in glob(f'{source_directory}/**/{base_pattern}{extension}',recursive=True) if os.path.getsize(file) < 500 * 1024]

    # Check if there are no files to copy
    if len(file_paths) == 0:
        print("No file found to copy.")
    else:
        # Initialize a file copy counter
        copy_counter = 0

        # Iterate over each file in the list
        for file_path in file_paths:
            # Check if the file exists
            if os.path.isfile(file_path):
                # Determine the relative path of the file
                relative_path = os.path.relpath(file_path, source_directory)
                # Create the corresponding directory in the destination folder
                destination_path = os.path.join(destination_folder, os.path.dirname(relative_path))
                os.makedirs(destination_path, exist_ok=True)

                # Get the size of the file in bytes
                total_size = os.path.getsize(file_path)

                # Get the correct drive of the destination folder
                destination_drive = os.path.splitdrive(destination_folder)[0]

                # Check if there is enough free space in the destination directory
                free_space = get_free_space(destination_drive)
                if free_space >= total_size:
                    # Generate a unique filename in the destination subdirectory
                    unique_destination_file = generate_unique_filename(file_path, destination_path)
                    # Use shutil.copy() to copy the file to the destination folder
                    shutil.copy(file_path, unique_destination_file)
                    copy_counter += 1  # Increment the counter
                else:
                    print("Error: Not Enough Free Space in the Destination Directory.")

        print(f"Total number of files copied: {copy_counter}")
```

    Total number of files copied: 6
    

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




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
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
      <td>AS_123_US.xlsx</td>
      <td>30</td>
      <td>2024-06-13 05:46 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\AS_123_US.xlsx</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Cor_US.docx</td>
      <td>46</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed\Cor_US.docx</td>
    </tr>
    <tr>
      <th>4</th>
      <td>gmail.txt</td>
      <td>0</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\gmail.txt</td>
    </tr>
    <tr>
      <th>5</th>
      <td>g_AS.txt</td>
      <td>0</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\g_AS.txt</td>
    </tr>
    <tr>
      <th>6</th>
      <td>g_US.xlsx</td>
      <td>30</td>
      <td>2024-06-13 05:01 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\g_US.xlsx</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Hello_US.csv</td>
      <td>1868</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\Hello_US.csv</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Test.xlsx</td>
      <td>30</td>
      <td>2024-06-18 10:38 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Test.xlsx</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Test1.xlsx</td>
      <td>31</td>
      <td>2024-08-11 10:53 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Test1.xlsx</td>
    </tr>
    <tr>
      <th>10</th>
      <td>US1234.txt</td>
      <td>0</td>
      <td>2024-06-13 04:46 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\US1234.txt</td>
    </tr>
    <tr>
      <th>11</th>
      <td>US_123_AS.xlsx</td>
      <td>30</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\US_123_AS.xlsx</td>
    </tr>
    <tr>
      <th>12</th>
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




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
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
      <td>AS_123_US.xlsx</td>
      <td>30</td>
      <td>2024-08-18 12:25 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed\AS_123_US.xlsx</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Test.xlsx</td>
      <td>30</td>
      <td>2024-08-17 10:56 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed\Test.xlsx</td>
    </tr>
    <tr>
      <th>2</th>
      <td>US1234.txt</td>
      <td>0</td>
      <td>2024-08-18 12:25 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Ali_Saeed\US1234.txt</td>
    </tr>
    <tr>
      <th>3</th>
      <td>US_123_AS.xlsx</td>
      <td>30</td>
      <td>2024-08-18 12:25 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed\US_123_AS.xlsx</td>
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
with pd.ExcelWriter("85_Example.xlsx",date_format = 'dd-mm-yyyy',datetime_format='dd-mm-yyyy') as writer:
    # Export File Information
    file_info_source_directory.to_excel(writer, sheet_name='Source',index=False)
    file_info_destination_folder.to_excel(writer, sheet_name='Destination',index=False)
```
