# Copying Files (Excluding Subfolders) That Start with Specific Characters and Handling Overwrites

## Description

This example combines the enhancements from previous examples. It excludes subfolders from the copy operation and handles potential overwrites by generating new filenames with incremental suffixes if a file with the same name already exists in the destination folder.

## Limitations

No significant limitations observed. The script effectively handles subfolder exclusion and potential overwrites, ensuring robust copy operations.


```python
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
        
        # If a file with the same name already exists, generate a new filename
        if os.path.exists(destination_file_path):
            base_filename, file_extension = os.path.splitext(file)
            counter = 1
            new_filename = f"{base_filename}_{counter}{file_extension}"
            new_destination_file_path = os.path.join(destination_folder, new_filename)
            while os.path.exists(new_destination_file_path):
                counter += 1
                new_filename = f"{base_filename}_{counter}{file_extension}"
                new_destination_file_path = os.path.join(destination_folder, new_filename)
            destination_file_path = new_destination_file_path

        # Copy the file to the destination folder
        shutil.copy(source_file_path, destination_file_path)
```
