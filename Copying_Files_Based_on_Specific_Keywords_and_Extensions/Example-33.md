# Copying Files with a Specific Extension and Containing a Specific Keyword

## Description

This script copies files from a source directory to a destination directory if their names contain the keyword "Al" and have a ".xlsx" extension. It ensures that only files matching these criteria are copied.

## Limitations

**Overwriting Existing Files:** If a file with the same name already exists in the destination folder, it will be overwritten without any warning or confirmation, potentially leading to data loss.


```python
# Import the required libraries
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
    # Check if the file extension is .xlsx
    if file.endswith('.xlsx'):
        # Get the base name without extension
        base_name, extension = os.path.splitext(file)

        # Check if the base name contains "Al"
        if 'Al' in base_name:
            # Set the full source and destination file paths
            source_file_path = os.path.join(file_path, file)
            destination_file_path = os.path.join(destination_folder, file)
            
            # Copy the file from source to destination
            shutil.copy(source_file_path, destination_file_path)
```
