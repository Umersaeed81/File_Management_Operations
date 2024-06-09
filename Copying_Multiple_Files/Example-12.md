# Example-12: Copying Only Files and Renaming to Avoid Overwrites

## Description


This example combines the functionality of filtering out subfolders and avoiding overwrites by renaming files. It ensures that only files are copied, and if a file with the same name already exists in the destination folder, it generates a new filename to prevent overwriting.


```python
# Import the required library
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Get the list of files (excluding subfolders) in the source directory
files = [f for f in os.listdir(file_path) if os.path.isfile(os.path.join(file_path, f))]

# Iterate over the files and copy each one to the destination folder
for file in files:
    source_file_path = os.path.join(file_path, file)
    destination_file_path = os.path.join(destination_folder, file)

    # If the file with the same name already exists, generate a new filename
    counter = 1
    while os.path.exists(destination_file_path):
        base_filename, file_extension = os.path.splitext(file)
        new_filename = os.path.join(destination_folder,\
                f"{base_filename}_{counter}{file_extension}")
        counter += 1
        destination_file_path = new_filename

    shutil.copy(source_file_path, destination_file_path)
```
