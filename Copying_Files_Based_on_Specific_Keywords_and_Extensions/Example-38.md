# Copying Files That End with Multiple Keywords and Have Multiple Extensions, Handling Overwrites

This script copies files from the source directory to the destination directory if their base names end with "AS" or "US" and have either a ".xlsx" or ".txt" extension. It also ensures that files are not overwritten by generating unique filenames.

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

# Get the list of files in the source directory
files = os.listdir(file_path)

# Iterate over the files
for file in files:
    source_file_path = os.path.join(file_path, file)

    # Get the base name without extension
    base_name, extension = os.path.splitext(file)

    # Check if the file ends with "AS" and "US" and has a ".xlsx" and ".txt" extension
    if base_name.endswith(('AS','US')) and file.lower().endswith((".xlsx",".txt")):
        destination_file_path = os.path.join(destination_folder, file)

        # If the file with the same name already exists, generate a new filename
        counter = 1
        while os.path.exists(destination_file_path):
            base_filename, file_extension = os.path.splitext(file)
            new_filename = os.path.join(destination_folder,\
                        f"{base_filename}_{counter}{file_extension}")
            counter += 1
            destination_file_path = new_filename

        # Copy the file to the destination folder
        shutil.copy(source_file_path, destination_file_path)
```
