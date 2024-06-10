# Copying Files That Start with a Specific Keyword and Have a Specific Extension, Handling Overwrites

## Description

This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

## Limitations

No significant limitations observed. The script effectively handles potential overwrites by renaming files.


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

        # If the file with the same name already exists, generate a new filename
        counter = 1
        while os.path.exists(destination_file_path):
            base_filename, file_extension = os.path.splitext(file)
            new_filename = os.path.join(destination_folder, \
                    f"{base_filename}_{counter}{file_extension}")
            counter += 1
            destination_file_path = new_filename

        # Copy the file to the destination
        shutil.copy(source_file_path, destination_file_path)
```
