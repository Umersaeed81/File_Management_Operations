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

## Copying a File with a Different Name

**Objective:** To copy a file named `03_PRS.csv` from one folder (Umer_Saeed) to another folder (Ali_Saeed) but with a different file name (`prs.csv`).


```python
import shutil
# Define the source and destination directory paths
file_path = "D:/Copy/Umer_Saeed/03_PRS.csv"
destination_folder = 'D:/Copy/Ali_Saeed/prs.csv'
shutil.copyfile(file_path, destination_folder)
```




    'D:/Copy/Ali_Saeed/prs.csv'



![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true)
