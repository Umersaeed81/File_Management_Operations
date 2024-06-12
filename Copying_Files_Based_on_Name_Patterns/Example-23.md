# Copying Files (Excluding Subfolders) That End with Specific Characters

## Description

In this example, the script is enhanced to exclude subfolders from the copy operation. It only processes and copies files that end with the specified characters.

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
            # Use the shutil.copy() function to copy the file
            shutil.copy(source_item_path, destination_item_path)
```
