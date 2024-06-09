#  [Umer Saeed](https://www.linkedin.com/in/engumersaeed/)
Sr. RF Planning & Optimization Engineer<br>
BSc Telecommunications Engineering, School of Engineering<br>
MS Data Science, School of Business and Economics<br>
**University of Management & Technology**<br>
**Mobile:**     +923018412180<br>
**Email:**  umersaeed81@hotmail.com<br>
**Address:** Dream Gardens,Defence Road, Lahore<br>

# Checking Source File Existence

Similar to [Example 1](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Single_File_Copying_Techniques/Example-01.md), but it includes a check to ensure that the source file exists before attempting to copy it. If the file exists, it performs the copy operation; otherwise, it prints an error message.

However, this code has the following limitations:

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

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/pic1.png?raw=true)


```python

```
