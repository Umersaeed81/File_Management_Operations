# Copying Files That Start with Specific Characters

## Description

This example demonstrates how to copy files from a source directory to a destination directory based on whether their names start with the characters "Al". The script iterates over the files in the source directory and copies those that match the condition to the destination folder.

## Limitations

**1. Overwriting Existing Files:** If a file with the same name already exists in the destination folder, it will be overwritten without any warning or confirmation, potentially leading to data loss.<br>
**2. Handling Subfolders:** The script will not correctly handle subfolders that start with the specified characters, as it is designed to copy files only.


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

# Iterate over the files
for file in files:
    source_file_path = os.path.join(file_path, file)

    # Check if the file starts with "Al"
    if file.startswith("Al"):
        destination_file_path = os.path.join(destination_folder, file)
        # Use the shutil.copy() function to copy the file
        shutil.copy(source_file_path, destination_file_path)
```
