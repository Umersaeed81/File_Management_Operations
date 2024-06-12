# Example-9: Copying All Files from a Directory

## Description

This example demonstrates how to copy all files from a source directory to a destination directory. It iterates over each file in the source directory and duplicates it in the destination directory.

## Limitations

**1. Handling Subfolders:** This script does not distinguish between files and subfolders. If subfolders are present, they will cause errors.<br>
**2. Overwriting Existing Files:** If files with the same names already exist in the destination folder, they will be overwritten without any warning, potentially leading to data loss.


```python
# Import the required library
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Get the list of files in the source directory
files = os.listdir(file_path)

# Iterate over the files and copy each one to the destination folder
for file in files:
    source_file_path = os.path.join(file_path, file)
    destination_file_path = os.path.join(destination_folder, file)
    # Use the shutil.copy() function to copy the file
    shutil.copy(source_file_path, destination_file_path)
```
