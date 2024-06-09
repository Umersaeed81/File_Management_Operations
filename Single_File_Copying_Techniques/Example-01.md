#  [Umer Saeed](https://www.linkedin.com/in/engumersaeed/)
Sr. RF Planning & Optimization Engineer<br>
BSc Telecommunications Engineering, School of Engineering<br>
MS Data Science, School of Business and Economics<br>
**University of Management & Technology**<br>
**Mobile:**     +923018412180<br>
**Email:**  umersaeed81@hotmail.com<br>
**Address:** Dream Gardens,Defence Road, Lahore<br>


# Basic Copy Operation

This code imports the **shutil** library, which provides functions for file operations. It sets the source file path and the destination folder path. Then, it uses **shutil.copy()** to copy the file from the source to the destination.

However, this code has the following limitations:

**1. Overwriting Existing Files:** If a file with the same name already exists in the destination folder, the existing file will be overwritten without any warning or confirmation, potentially leading to data loss.<br />
**2. Non-existent Source File:** If the source file does not exist, an error will occur.<br />
**3. Non-existent Destination Folder:** If the destination folder does not exist, the code will not copy the file correctly.<br />



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

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/pic1.png?raw=true)
