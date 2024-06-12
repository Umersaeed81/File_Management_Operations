# Copying Excel and Text Files

## Description

This example extends the filtering criteria to include both .xlsx and .txt files. It demonstrates how to copy multiple specific file types from a source directory to a destination directory.

## Limitations

**Overwriting Existing Files:** If files with the same names already exist in the destination folder, they will be overwritten without any warning, potentially leading to data loss.


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

# Iterate over the files and copy only .xlsx files to the destination folder
for file in files:
    if file.endswith((".xlsx",".txt")):
        source_file_path = os.path.join(file_path, file)
        destination_file_path = os.path.join(destination_folder, file)
        # Use the shutil.copy() function to copy the file
        shutil.copy(source_file_path, destination_file_path)
```
