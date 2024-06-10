# Copying Files with a Specific Extension and Containing a Specific Keyword, Handling Overwrites

## Description

This example combines the conditions of Example 33 with the overwrite handling of previous examples. It copies files whose names contain the keyword "Al" and have a ".xlsx" extension, and if a file with the same name already exists in the destination folder, it generates a new filename to avoid overwriting.

## Limitations

No significant limitations observed. The script effectively handles potential overwrites by renaming files.


```python
# Import the required libraries
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
    # Check if the file extension is .xlsx
    if file.endswith('.xlsx'):
        # Get the base name without extension
        base_name, extension = os.path.splitext(file)

        # Check if the base name contains "Al"
        if 'Al' in base_name:
            # Set the full source and destination file paths
            source_file_path = os.path.join(file_path, file)
            destination_file_path = os.path.join(destination_folder, file)
            
            # Handle existing file names by appending a counter
            counter = 1
            new_filename = destination_file_path
            while os.path.exists(new_filename):
                base_filename, file_extension = os.path.splitext(file)
                new_filename = os.path.join(destination_folder, f"{base_filename}_{counter}{file_extension}")
                counter += 1
            
            # Copy the file from source to the new filename in the destination
            shutil.copy(source_file_path, new_filename)
```
