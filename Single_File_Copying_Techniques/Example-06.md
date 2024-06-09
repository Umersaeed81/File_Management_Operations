#  [Umer Saeed](https://www.linkedin.com/in/engumersaeed/)
Sr. RF Planning & Optimization Engineer<br>
BSc Telecommunications Engineering, School of Engineering<br>
MS Data Science, School of Business and Economics<br>
**University of Management & Technology**<br>
**Mobile:**     +923018412180<br>
**Email:**  umersaeed81@hotmail.com<br>
**Address:** Dream Gardens,Defence Road, Lahore<br>

# Handling Filename Conflicts

This code checks if the source file exists and ensures that the destination folder is created if it does not already exist. If a file with the same name exists in the destination folder, it generates a new filename with an incremental suffix to avoid overwriting existing files. If the source file is not found, an error message is displayed.


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
    # Check if the destination folder exists, create it if not
    os.makedirs(destination_folder, exist_ok=True)

    # Get the base filename and file extension
    base_filename, file_extension = os.path.splitext(os.path.basename(file_path))

    # Generate a new filename with an incremental suffix
    new_filename = os.path.join(destination_folder, base_filename + file_extension)

    counter = 1
    while os.path.exists(new_filename):
        new_filename = os.path.join(destination_folder, f"{base_filename}_{counter}{file_extension}")
        counter += 1

    # Use the shutil.copy() function to copy the file
    shutil.copy(file_path, new_filename)
    print("File copied successfully!")
else:
    print(f"Error: File not found at {file_path}")
```

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/pic1.png?raw=true)


```python

```
