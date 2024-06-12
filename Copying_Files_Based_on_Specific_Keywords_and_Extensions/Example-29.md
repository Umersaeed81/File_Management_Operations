# Copying Files That Start with a Specific Keyword and Have a Specific Extension

## Description

This script copies files from a source directory to a destination directory if their names start with "Al" and have a ".xlsx" extension. It iterates over the files in the source directory and copies those that match the conditions to the destination folder.

## Limitations

**Overwriting Existing Files:** If a file with the same name already exists in the destination folder, it will be overwritten without any warning or confirmation, potentially leading to data loss.


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

    # Check if the file starts with "AI" and has a ".xlsx" extension
    if file.startswith("Al") and file.lower().endswith(".xlsx"):
        destination_file_path = os.path.join(destination_folder, file)
        # Use the shutil.copy() function to copy the file
        shutil.copy(source_file_path, destination_file_path)
```
