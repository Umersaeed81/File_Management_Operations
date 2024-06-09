# Example-7: Selective Files Copy

## Description

This example demonstrates how to selectively copy multiple files from a list of source files to a destination folder. The code checks if each file exists and copies it if it does. If the destination folder does not exist, it is created.

## Limitations

**Overwriting Existing Files:** If files with the same names already exist in the destination folder, the existing files will be overwritten without any warning or confirmation, potentially leading to data loss.


```python
import os
import shutil

# Define source files and destination folder
source_files = ["D:/Copy/Umer_Saeed/Test.xlsx", "D:/Copy/Umer_Saeed/Test1.xlsx"]
destination_folder = "D:/Copy/Ali_Saeed"



# Copy files to the destination folder
for file_path in source_files:
    # Check if the destination folder exists, create it if not
    os.makedirs(destination_folder, exist_ok=True)
    if os.path.exists(file_path):
        shutil.copy(file_path, destination_folder)
        print(f"Copied: {file_path} to {destination_folder}")
    else:
        print(f"File not found: {file_path}")
```
