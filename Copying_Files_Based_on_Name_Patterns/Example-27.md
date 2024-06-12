# Copying Files (Excluding Subfolders) That Contain Specific Keywords

## Description

In this example, the script is enhanced to exclude subfolders from the copy operation. It only processes and copies files that contain the specified keyword.

## Limitations

**Overwriting Existing Files:** If a file with the same name already exists in the destination folder, it will be overwritten without any warning or confirmation, potentially leading to data loss.


```python
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

        # Copy the file to the destination folder
        shutil.copy(source_file_path, destination_file_path)
```
