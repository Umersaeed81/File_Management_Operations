# Example-4: Comprehensive Error Handling

## Description

This version combines checks for both the existence of the source file and the destination folder before performing the copy operation, providing more comprehensive error handling compared to previous examples.

## Limitations

**Overwriting Existing Files:** If a file with the same name already exists in the destination folder, the existing file will be overwritten without any warning or confirmation, potentially leading to data loss.


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
    # Check if the destination folder exists
    if not os.path.exists(destination_folder):
        print(f"Error: Destination folder '{destination_folder}' not found.")
    else:
        # Use the shutil.copy() function to copy the file
        shutil.copy(file_path, destination_folder)
        print(f"File copied successfully from '{file_path}' to '{destination_folder}'.")
else:
    print(f"Error: File not found at {file_path}")
```
