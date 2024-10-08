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

# Copy Multiple Prefixes ("US" or "AS") Files


This example illustrates the process of copying files from the subdirectories of a specified source directory, but not from the source directory itself, to a destination directory based on multiple filename prefixes (in this case, **"US"** or **"AS"**). It involves several steps to ensure efficient and error-free file transfer:

-  **SourceDirectory Check:** The code checks for the existence of the source directory. If the source directory is not found, an error message is displayed. If no files are found in the source directory to copy, it displays a message indicating this condition.
- **Space Check:** Before copying each file, it verifies that there is enough free space in the target directory's drive to accommodate the file. If there is not enough free space, an error message is displayed.
- **Unique Filename Generation:** If a file with the same name already exists in the target folder, it generates a unique filename to prevent overwriting existing files.
- **Automatic Target Folder Creation:** If the target folder does not exist, it is automatically created before copying files.
-  **File Copying:** The code uses `shutil.copyfile()` to copy each file. This function updates the file's metadata, so the last modification time reflects the current time of the copy operation rather than the original file’s modification time.
- **File Copy Report:** After processing all files, it reports the total number of files successfully copied.
- **Metadata Collection and Export:**
    - **File Metadata:** Metadata for the files in both the source and destination directories is gathered. This includes file name, size, last modification time, file extension, and the full file path.
    - **Excel Export:** The collected metadata is exported to an Excel file with two sheets: one for the source directory and another for the destination directory.

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
source_directory = 'D:/Copy/Umer_Saeed/'
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
    # Define the file name patterns
    patterns = ['US*.*', 'AS*.*']
    # Define the file paths
    file_paths = [file for pattern in patterns for file in glob(f'{source_directory}/**/{pattern}',recursive=False)]

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
                # Check if the destination folder exists, create it if not
                os.makedirs(destination_folder, exist_ok=True)

                # Get the size of the file in bytes
                total_size = os.path.getsize(file_path)

                # Get the correct drive of the destination folder
                destination_drive = os.path.splitdrive(destination_folder)[0]

                # Check if there is enough free space in the destination directory
                free_space = get_free_space(destination_drive)
                if free_space >= total_size:
                    # Generate a unique filename in the destination folder
                    unique_destination_file = generate_unique_filename(file_path, destination_folder)
                    # Use shutil.copyfile() to copy the file to the destination folder
                    shutil.copyfile(file_path, unique_destination_file)
                    copy_counter += 1  # Increment the counter
                else:
                    print("Error: Not Enough Free Space in the Destination Directory.")

        print(f"Total number of files copied: {copy_counter}")
```

    Total number of files copied: 7
    

## Gathering and Formatting File Metadata


```python
def get_file_info(path):
    # Get the list of files
    file_list = glob(f'{path}')


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
file_info_source_directory = get_file_info('D:/Copy/Umer_Saeed/**/*.*')
file_info_destination_folder = get_file_info('D:/Copy/Ali_Saeed/*.*')        # Only files from subdirectories
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
      <th>Created Date</th>
      <th>Modified Date</th>
      <th>File Extension</th>
      <th>Full File Path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>g</td>
      <td>0</td>
      <td>2024-08-13 07:30 PM</td>
      <td>2024-08-13 07:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\BH</td>
    </tr>
    <tr>
      <th>1</th>
      <td>a</td>
      <td>1868</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>2</th>
      <td>AS_1234_US</td>
      <td>30</td>
      <td>2024-08-11 03:54 PM</td>
      <td>2024-08-11 03:54 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>b</td>
      <td>1</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-06-12 06:36 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>4</th>
      <td>c</td>
      <td>30</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-06-12 06:35 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>5</th>
      <td>d</td>
      <td>1868</td>
      <td>2024-08-11 11:43 AM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Hello_t_US</td>
      <td>1868</td>
      <td>2024-08-11 03:32 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>7</th>
      <td>US1234_Salam</td>
      <td>0</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-13 04:46 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>8</th>
      <td>US_123_AS_Hello</td>
      <td>30</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>9</th>
      <td>US_Test_Hi</td>
      <td>4201</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1234_US_G</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>11</th>
      <td>15031984_AliSaeed</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>12</th>
      <td>19980802_UmerSaeed</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Babar_Azam</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Cor_US</td>
      <td>46</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>15</th>
      <td>gmail</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>16</th>
      <td>g_AS</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Ijlal_Khan</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Pakistan_1947-08-14</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>19</th>
      <td>US1234</td>
      <td>1</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:24 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>20</th>
      <td>US_123_AS</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>21</th>
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




```python
file_info_destination_folder
```





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
      <td>AS_1234_US</td>
      <td>30</td>
      <td>2024-09-20 05:58 PM</td>
      <td>2024-09-20 05:58 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed</td>
    </tr>
    <tr>
      <th>1</th>
      <td>US1234</td>
      <td>1</td>
      <td>2024-09-20 05:58 PM</td>
      <td>2024-09-20 05:58 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Ali_Saeed</td>
    </tr>
    <tr>
      <th>2</th>
      <td>US1234_Salam</td>
      <td>0</td>
      <td>2024-09-20 05:58 PM</td>
      <td>2024-09-20 05:58 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Ali_Saeed</td>
    </tr>
    <tr>
      <th>3</th>
      <td>US_123_AS</td>
      <td>30</td>
      <td>2024-09-20 05:58 PM</td>
      <td>2024-09-20 05:58 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed</td>
    </tr>
    <tr>
      <th>4</th>
      <td>US_123_AS_Hello</td>
      <td>30</td>
      <td>2024-09-20 05:58 PM</td>
      <td>2024-09-20 05:58 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed</td>
    </tr>
    <tr>
      <th>5</th>
      <td>US_Test</td>
      <td>4201</td>
      <td>2024-09-20 05:58 PM</td>
      <td>2024-09-20 05:58 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed</td>
    </tr>
    <tr>
      <th>6</th>
      <td>US_Test_Hi</td>
      <td>4201</td>
      <td>2024-09-20 05:58 PM</td>
      <td>2024-09-20 05:58 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Ali_Saeed</td>
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
with pd.ExcelWriter("08_Example.xlsx",date_format = 'dd-mm-yyyy',datetime_format='dd-mm-yyyy') as writer:
    # Export File Information
    file_info_source_directory.to_excel(writer, sheet_name='Source',index=False)
    file_info_destination_folder.to_excel(writer, sheet_name='Destination',index=False)
```

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true)
