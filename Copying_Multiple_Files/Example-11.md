# Example-11: Copying Only Files from a Directory

## Description

This example refines the copying process by filtering out subfolders and only copying files from the source directory to the destination directory. This ensures that only the intended files are copied without including any subfolder structures.

## Limitations

**Overwriting Existing Files:** This script does not handle filename conflicts. If files with identical names already exist in the destination folder, they will be overwritten without warning, potentially leading to data loss.


```python
# Import the required library
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed/"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Get the list of files (excluding subfolders) in the source directory
files = [f for f in os.listdir(file_path) if os.path.isfile(os.path.join(file_path, f))]

# Iterate over the files and copy each one to the destination folder
for file in files:
    source_file_path = os.path.join(file_path, file)
    destination_file_path = os.path.join(destination_folder, file)
    # Use the shutil.copy() function to copy the file
    shutil.copy(source_file_path, destination_file_path)
```
