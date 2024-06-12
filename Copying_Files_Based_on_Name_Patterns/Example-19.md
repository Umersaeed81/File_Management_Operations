# Copying Files (Excluding Subfolders) That Start with Specific Characters

## Description

In this example, the script is enhanced to exclude subfolders from the copy operation.

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

    # Check if the item is a file and starts with "Al"
    if os.path.isfile(source_file_path) and file.startswith("Al"):
        destination_file_path = os.path.join(destination_folder, file)
        shutil.copy(source_file_path, destination_file_path)
```
