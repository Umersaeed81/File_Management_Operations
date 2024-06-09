# Example-1:Basic File Copy

## Description

This example demonstrates how to copy a single file from a source location to a destination folder using the **shutil.copy()** function. This operation creates an exact copy of the file in the specified destination.

## Limitations

**1. Overwriting Existing Files:** If a file with the same name already exists in the destination folder, the existing file will be overwritten without any warning or confirmation, potentially leading to data loss.<br>
**2. Non-existent Source File:** If the source file does not exist, an error will occur.<br>
**3. Non-existent Destination Folder:** If the destination folder does not exist, the code will not copy the file correctly.


```python
# Import the required library
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed/Test.xlsx"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Use the shutil.copy() function to copy the file
shutil.copy(file_path, destination_folder)
```
