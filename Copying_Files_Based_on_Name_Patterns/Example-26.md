# Copying Files That Contain Specific Keywords and Handling Overwrites

## Description

This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

## Limitations

**Handling Subfolders:** The script works well unless a subfolder's name contains the specified keyword, in which case it might raise an error.


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

    # Get the base name without extension
    base_name, extension = os.path.splitext(file)

    # Check if the base name contains "Al"
    if 'Al' in base_name:
        destination_file_path = os.path.join(destination_folder, file)
        
        
        counter = 1
        new_filename = destination_file_path
        while os.path.exists(new_filename):
            base_filename, file_extension = os.path.splitext(destination_file_path)
            new_filename = os.path.join(destination_folder, f"{base_filename}_{counter}{file_extension}")
            counter += 1
        # Use the shutil.copy() function to copy the file
        shutil.copy(source_file_path, new_filename)
```
