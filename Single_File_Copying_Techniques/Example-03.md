# Checking Destination Folder Existence


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

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/pic1.png?raw=true)


```python

```
