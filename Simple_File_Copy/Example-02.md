# Example-2: File Copy with Existence Check

## Description

This example enhances the basic file copy by first checking if the source file exists before attempting to copy it. If the file is found, it is copied to the destination folder, and a success message is printed. If not, an error message is displayed.

## Limitations

**1. Overwriting Existing Files:** If a file with the same name already exists in the destination folder, the existing file will be overwritten without any warning or confirmation, potentially leading to data loss.<br>
**2. Non-existent Destination Folder:** If the destination folder does not exist, the code will not copy the file correctly.


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
    # Use the shutil.copy() function to copy the file
    shutil.copy(file_path, destination_folder)
    print("File copied successfully!")
else:
    print(f"Error: File not found at {file_path}")
```
