# Example-10: Copying All Files and Renaming to Avoid Overwrites

## Description

This example improves upon the previous one by adding functionality to avoid overwriting existing files in the destination folder. It generates new filenames with an incremental suffix if a file with the same name already exists.

## Limitations

**Handling Subfolders:** Similar to the previous example, this script does not handle subfolders and will raise an error if any are found in the source directory.


```python
# Import the required library
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Iterate over all files in the source folder
for filename in os.listdir(file_path):
    source_file = os.path.join(file_path, filename)
    destination_file = os.path.join(destination_folder, filename)
    """
    If the file with the same name already exists in the destination folder, 
    generate a new filename
    """
    if os.path.exists(destination_file):
        base_filename, file_extension = os.path.splitext(filename)
        new_filename = os.path.join(destination_folder, f"{base_filename}_1{file_extension}")

        counter = 1
        while os.path.exists(new_filename):
            new_filename = os.path.join(destination_folder, \
            f"{base_filename}_{counter}{file_extension}")
            counter += 1

        destination_file = new_filename

    # Copy the file to the destination folder
    shutil.copy(source_file, destination_file)
```
