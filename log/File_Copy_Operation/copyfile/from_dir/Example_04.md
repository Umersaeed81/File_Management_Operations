<table style="border-collapse: collapse;">
  <tr>
    <td style="vertical-align: top;">
      <h1><a href="https://www.linkedin.com/in/engumersaeed/">Umer Saeed</a></h1>
      Sr. RF Planning & Optimization Engineer<br>
      BSc Telecommunications Engineering, School of Engineering<br>
      MS Data Science, School of Business and Economics<br>
      <strong>University of Management & Technology</strong><br>
      <strong>Mobile:</strong> +923018412180<br>
      <strong>Email:</strong> umersaeed81@hotmail.com<br>
      <strong>Address:</strong> Dream Gardens, Defence Road, Lahore<br>
    </td>
    <td style="vertical-align: top; padding-left: 100px;">
      <img src="https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true" alt="Bano Qabil Logo" width="500"/>
    </td>
  </tr>
</table>

## Importing Required Modules


```python
import os
import shutil
```

## Setting Source File and Destination Folder Path


```python
# List of files to copy
files_to_copy = ["D:/Copy/Umer_Saeed/03_PRS.csv",
    "D:/Copy/Umer_Saeed/Hello_US.csv",
    "D:/Copy/Umer_Saeed/Cor_US.docx"]

# Destination folder
destination_folder = 'D:/Copy/Ali_Saeed/'
```

## Copying the Files to the Destination


```python
# Loop over each file and copy it
for file_path in files_to_copy:
    # Get the file name from the file path
    file_name = os.path.basename(file_path)
    # Define the destination path
    destination_path = os.path.join(destination_folder, file_name)
    try:
        # Copy each file
        shutil.copyfile(file_path, destination_path)
        print(f'Copied: {file_path} to {destination_path}')
    except IOError:
        print(f'Error copying file: {file_path}')
```

    Copied: D:/Copy/Umer_Saeed/03_PRS.csv to D:/Copy/Ali_Saeed/03_PRS.csv
    Copied: D:/Copy/Umer_Saeed/Hello_US.csv to D:/Copy/Ali_Saeed/Hello_US.csv
    Copied: D:/Copy/Umer_Saeed/Cor_US.docx to D:/Copy/Ali_Saeed/Cor_US.docx
    

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true)
