# Copying Files (Excluding Subfolders) That End with Specific Characters and Handling Overwrites

## Description

This example combines the enhancements from previous examples. It excludes subfolders from the copy operation and handles potential overwrites by generating new filenames with incremental suffixes if a file with the same name already exists in the destination folder.

## Limitations

No significant limitations observed. The script effectively handles subfolder exclusion and potential overwrites, ensuring robust copy operations.


```python
# Import the required library
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Get the list of items in the source directory
items = os.listdir(file_path)

# Iterate over the items
for item in items:
    source_item_path = os.path.join(file_path, item)

    # Ensure we are only processing files, not directories
    if os.path.isfile(source_item_path):
        # Get the base name without extension
        base_name, extension = os.path.splitext(item)

        # Check if the base name ends with "_gl"
        if base_name.endswith('_gl'):
            destination_item_path = os.path.join(destination_folder, item)
            
            # If the file with the same name already exists, generate a new filename
            if os.path.exists(destination_item_path):
                counter = 1
                new_filename = f"{base_name}_{counter}{extension}"
                new_destination_item_path = os.path.join(destination_folder, new_filename)
                while os.path.exists(new_destination_item_path):
                    counter += 1
                    new_filename = f"{base_name}_{counter}{extension}"
                    new_destination_item_path = os.path.join(destination_folder, new_filename)
                destination_item_path = new_destination_item_path
            
            # Copy the file to the destination folder
            shutil.copy(source_item_path, destination_item_path)
```
