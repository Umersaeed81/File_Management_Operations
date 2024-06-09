# Example-3:File Copy with Destination Folder Check

## Description

This example further improves the file copy operation by checking if the destination folder exists. If the destination folder is not found, an error message is displayed, preventing the copy operation from proceeding.

## Limitations

However, this code has the following limitations:

**1. Overwriting Existing Files:** If a file with the same name already exists in the destination folder, the existing file will be overwritten without any warning or confirmation, potentially leading to data loss.<br>
**2. Non-existent Source File:** If the source file does not exist, an error will occur.


```python
# Import the required library
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed/Test.xlsx"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"


# Check if the destination folder exists
if not os.path.exists(destination_folder):
    print(f"Error: Destination folder '{destination_folder}' not found.")
else:
    # Use the shutil.copy() function to copy the file
    shutil.copy(file_path, destination_folder)
    print(f"File copied successfully from '{file_path}' to '{destination_folder}'.")
```
