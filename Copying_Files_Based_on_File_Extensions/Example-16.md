# Copying Excel and Text Files with Renaming to Avoid Overwrites

## Description

This example combines the functionality of copying specific file types and renaming files to avoid overwrites. It filters files by .xlsx and .txt extensions and ensures that if a file with the same name already exists in the destination folder, a new filename is generated to prevent overwriting.

## Limitations

**Performance Concerns:** Generating new filenames incrementally can become inefficient if the destination folder contains a large number of files, potentially leading to performance issues.<br>
**Error Handling:** The script does not include comprehensive error handling for potential issues such as insufficient permissions or disk space.


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

# Iterate over the files and copy only .xlsx files to the destination folder
for file in files:
    if file.endswith((".xlsx", ".txt")):
        source_file_path = os.path.join(file_path, file)
        destination_file_path = os.path.join(destination_folder, file)

        # If the file with the same name already exists, generate a new filename
        counter = 1
        while os.path.exists(destination_file_path):
            base_filename, file_extension = os.path.splitext(file)
            new_filename = os.path.join(destination_folder, \
                    f"{base_filename}_{counter}{file_extension}")
            counter += 1
            destination_file_path = new_filename

        # Copy the file to the destination folder
        shutil.copy(source_file_path, destination_file_path)
```
