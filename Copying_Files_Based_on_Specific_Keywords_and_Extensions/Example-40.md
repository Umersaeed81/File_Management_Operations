# Copying Files That Contain Multiple Keywords and Have Multiple Extensions, Handling Overwrites

## Description

This script copies files from the source directory to the destination directory if their names contain "AS" or "US" and have either a ".xlsx" or ".txt" extension. It also ensures that files are not overwritten by generating unique filenames.

## Limitations

No limitations observed.


```python
# Import the required library
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Substrings to check for in the file name
target_substrings = ("AS", "US")

# Get the list of files in the source directory (not subdirectories)
files = os.listdir(file_path)

# Filter files based on the conditions
filtered_files = [file for file in files if file.endswith(('.xlsx', '.txt')) \
            and any(substring in file for substring in target_substrings)]

# Iterate over the filtered files and copy them
for file in filtered_files:
    source_file_path = os.path.join(file_path, file)
    destination_file_path = os.path.join(destination_folder, file)
    
    # If the file with the same name already exists, generate a new filename
    counter = 1
    while os.path.exists(destination_file_path):
        base_filename, file_extension = os.path.splitext(file)
        new_filename = f"{base_filename}_{counter}{file_extension}"
        destination_file_path = os.path.join(destination_folder, new_filename)
        counter += 1
    
    # Copy the file to the destination folder
    shutil.copy(source_file_path, destination_file_path)

print("Required files copied successfully.")

```
