# Copying Files That End with a Specific Keyword and Have a Specific Extension, Handling Overwrites

## Description

This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

## Limitations

No significant limitations observed. The script effectively handles potential overwrites by renaming files.


```python
# Import the required library
import os
import shutil

# Set the source folder path
source_folder = "D:/Copy/Umer_Saeed"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Get the list of files in the source directory
files = os.listdir(source_folder)

# Iterate over the files
for file in files:
    source_file_path = os.path.join(source_folder, file)

    # Get the base name without extension
    base_name, extension = os.path.splitext(file)

    # Check if the base name ends with "_Al" and the file has a ".xlsx" extension
    if base_name.endswith('_Al') and file.lower().endswith(".xlsx"):
        destination_file_path = os.path.join(destination_folder, file)

        # If the file with the same name already exists, generate a new filename
        counter = 1
        while os.path.exists(destination_file_path):
            base_filename, file_extension = os.path.splitext(file)
            new_filename = os.path.join(destination_folder, f"{base_filename}_{counter}{file_extension}")
            counter += 1
            destination_file_path = new_filename

        # Copy the file to the destination folder
        shutil.copy(source_file_path, destination_file_path)
```
