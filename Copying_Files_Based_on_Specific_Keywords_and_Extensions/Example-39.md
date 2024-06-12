# Copying Files That Contain Multiple Keywords and Have Multiple Extensions

## Description

This script copies files from the source directory to the destination directory if their names contain "AS" or "US" and have either a ".xlsx" or ".txt" extension.

## Limitations

**Overwriting Existing Files:** If a file with the same name already exists in the destination folder, it will be overwritten without any warning or confirmation, potentially leading to data loss.


```python
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Substrings to check for in the file name
target_substrings = ("AS", "US")

# Get the list of files in the source directory (not subdirectories)
files = os.listdir(file_path)

# Filter files based on the conditions
filtered_files = [file for file in files if file.endswith(('.xlsx', '.txt')) and any(substring in file for substring in target_substrings)]

# Iterate over the filtered files and copy them
for file in filtered_files:
    source_file_path = os.path.join(file_path, file)
    destination_file_path = os.path.join(destination_folder, file)
    
    # Copy the file to the destination folder
    shutil.copy(source_file_path, destination_file_path)

print("Required files copied successfully.")

```
