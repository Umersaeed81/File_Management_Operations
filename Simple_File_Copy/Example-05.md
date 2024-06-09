# Example-5: Creating Destination Folder

## Description

This code creates the destination folder if it does not already exist and checks if the source file exists. If the source file is found, it copies the file; otherwise, it displays an error message.

## Limitations

**Overwriting Existing Files:** If a file with the same name already exists in the destination folder, the existing file will be overwritten without any warning or confirmation, potentially leading to data loss.


```python
# Import the required libraries
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
    # Use the shutil.copy() function to copy the file
    shutil.copy(file_path, destination_folder)
    print("File copied successfully!")
else:
    print(f"Error: File not found at {file_path}")
```


```python

```
