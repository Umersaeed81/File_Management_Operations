# Copying Files That Start with Multiple Keywords and Have Multiple Extensions

# Description

This script copies files from the source directory to the destination directory if their names start with "AS" or "US" and have either a ".xlsx" or ".txt" extension.

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

    # Check if the file starts with "AS" and "US" and has a ".xlsx" and ".txt" extension
    if file.startswith(("AS",'US')) and file.lower().endswith((".xlsx",".txt")):
        destination_file_path = os.path.join(destination_folder, file)
        # Copy the file to the destination
        shutil.copy(source_file_path, destination_file_path)
```
