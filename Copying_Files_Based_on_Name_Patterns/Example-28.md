# Copying Files (Excluding Subfolders) That Contain Specific Keywords and Handling Overwrites

## Description

This example combines the enhancements from previous examples. It excludes subfolders from the copy operation and handles potential overwrites by generating new filenames with incremental suffixes if a file with the same name already exists in the destination folder.

## Limitations

No significant limitations observed. The script effectively handles subfolder exclusion and potential overwrites, ensuring robust copy operations.


```python
# Import the required library
import os
import shutil

# Set the source folder path
source_folder = "D:/Copy/Umer_Saeed"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Get the list of files directly in the source directory (excluding subdirectories)
files = [f for f in os.listdir(source_folder) if os.path.isfile(os.path.join(source_folder, f))]

# Iterate over the files
for file in files:
    source_file_path = os.path.join(source_folder, file)

    # Get the base name without extension
    base_name, extension = os.path.splitext(file)

    # Check if the base name contains "Al"
    if 'Al' in base_name:
        # Construct the destination file path
        destination_file_path = os.path.join(destination_folder, file)

        
        counter = 1
        new_filename = destination_file_path
        while os.path.exists(new_filename):
            base_filename, file_extension = os.path.splitext(destination_file_path)
            new_filename = os.path.join(destination_folder, f"{base_filename}_{counter}{file_extension}")
            counter += 1
        
        # Copy the file to the destination folder
        shutil.copy(source_file_path, new_filename)  # Copy file after applying renaming logic
```
