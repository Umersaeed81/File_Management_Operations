#  [Umer Saeed](https://www.linkedin.com/in/engumersaeed/)
Sr. RF Planning & Optimization Engineer<br>
BSc Telecommunications Engineering, School of Engineering<br>
MS Data Science, School of Business and Economics<br>
**University of Management & Technology**<br>
**Mobile:**     +923018412180<br>
**Email:**  umersaeed81@hotmail.com<br>
**Address:** Dream Gardens,Defence Road, Lahore<br>

# Checking Destination Folder Existence

This example extends the previous one by adding a check to ensure the destination folder exists before copying the file. If the folder does not exist, an error message is printed; otherwise, the copy operation proceeds.

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

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/pic1.png?raw=true)


```python

```
