# Creating Destination Folder


```python
# Import the required libraries
import os
import shutil

# Set the source file path
file_path = "D:/Copy/Umer_Saeed/Test.xlsx"
# Set the destination folder path
destination_folder = "D:/Copy/Ali_Saeed"

# Check if the destination folder exists, create it if not
os.makedirs(destination_folder, exist_ok=True)

# Check if the source file exists
if os.path.exists(file_path):
    # Use the shutil.copy() function to copy the file
    shutil.copy(file_path, destination_folder)
    print("File copied successfully!")
else:
    print(f"Error: File not found at {file_path}")
```

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/pic1.png?raw=true)


```python

```
