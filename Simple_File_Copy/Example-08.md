# Example-8: Selective Files Copy Avoiding Overwrites by Renaming

## Description

This example extends the selective files copy by adding functionality to avoid overwriting existing files in the destination folder. If a file with the same name already exists, the code generates a new filename with an incremental suffix to ensure that each file is copied without overwriting any existing files.

## Limitations

No significant limitations noted for this example as it handles file overwrites by renaming the file.


```python
import os
import shutil

# Define source files and destination folder
source_files = ["D:/Copy/Umer_Saeed/Test.xlsx", "D:/Copy/Umer_Saeed/Test1.xlsx"]
destination_folder = "D:/Copy/Ali_Saeed"

# # Ensure destination folder exists
# os.makedirs(destination_folder, exist_ok=True)

# Copy files to the destination folder with incremental filenames if necessary
for file_path in source_files:
    # Check if the destination folder exists, create it if not
    os.makedirs(destination_folder, exist_ok=True)
    if os.path.exists(file_path):
        # Get the base filename and file extension
        base_filename, file_extension = os.path.splitext(os.path.basename(file_path))

        # Generate a new filename with an incremental suffix if needed
        new_filename = os.path.join(destination_folder, base_filename + file_extension)
        counter = 1
        while os.path.exists(new_filename):
            new_filename = os.path.join(destination_folder, f"{base_filename}_{counter}{file_extension}")
            counter += 1

        # Use the shutil.copy() function to copy the file
        shutil.copy(file_path, new_filename)
        print(f"Copied: {file_path} to {new_filename}")
    else:
        print(f"File not found: {file_path}")
```
