# Example-6: Avoiding Overwrites by Renaming

## Description

This example ensures that the copied file does not overwrite an existing file in the destination folder by appending an incremental suffix to the filename if a file with the same name already exists. This guarantees that all copies are retained uniquely.

## Limitations

No significant limitations noted for this example as it handles file overwrites by renaming the file.


```python
# Import the required library
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed/Test.xlsx"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Check if the source file exists
if os.path.exists(file_path):
    # Check if the destination folder exists, create it if not
    os.makedirs(destination_folder, exist_ok=True)

    # Get the base filename and file extension
    base_filename, file_extension = os.path.splitext(os.path.basename(file_path))

    # Generate a new filename with an incremental suffix
    new_filename = os.path.join(destination_folder, base_filename + file_extension)

    counter = 1
    while os.path.exists(new_filename):
        new_filename = os.path.join(destination_folder, f"{base_filename}_{counter}{file_extension}")
        counter += 1

    # Use the shutil.copy() function to copy the file
    shutil.copy(file_path, new_filename)
    print("File copied successfully!")
else:
    print(f"Error: File not found at {file_path}")
```


```python

```
