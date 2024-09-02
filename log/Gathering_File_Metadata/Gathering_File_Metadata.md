## Retrieve and Display File Metadata Including Name, Size, Creation Date, Modification Date, Extension, and Directory Path

The goal of this code is to gather and present detailed information about the files in a specific folder. It provides a list showing each file's name (without the extension), size, when it was created, when it was last modified, its type, and the folder it is located in.


```python
# import required libraries
import os
import math
import pandas as pd
from glob import glob

# user define funcation
def get_file_info(path):
    # Get the list of files
    file_list = glob(f'{path}/**/*.*',recursive=True)

    # Using list comprehension to collect file details
    file_info = [(os.path.splitext(os.path.basename(file_path))[0],  # File name without extension
                  math.ceil(os.path.getsize(file_path) / 1024),  # File size in KB, rounded up
                  pd.to_datetime(os.path.getctime(file_path), unit='s')  # File creation time in UTC
                  .tz_localize('UTC')  # Localize to UTC
                  .tz_convert('Asia/Karachi')  # Convert to your local timezone
                  .strftime('%Y-%m-%d %I:%M %p'),  # Format as date and time
                  pd.to_datetime(os.path.getmtime(file_path), unit='s')  # Last modification time in UTC
                  .tz_localize('UTC')  # Localize to UTC
                  .tz_convert('Asia/Karachi')  # Convert to your local timezone
                  .strftime('%Y-%m-%d %I:%M %p'),  # Format as date and time
                  os.path.splitext(file_path)[1].lower(),  # File extension
                  os.path.dirname(file_path)  # Directory path without file name and extension
                 )
                 for file_path in file_list]

    # Create a DataFrame
    df = pd.DataFrame(file_info, columns=['File Name', 'File Size (KB)',
                                          'Created Date', 'Modified Date',
                                          'File Extension', 'Full File Path'])
    return df

# Get file information from the source and destination directories
df0 = get_file_info('D:/Copy/Umer_Saeed')

# Display the DataFrame
df0
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>File Name</th>
      <th>File Size (KB)</th>
      <th>Created Date</th>
      <th>Modified Date</th>
      <th>File Extension</th>
      <th>Full File Path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>03_PRS</td>
      <td>1868</td>
      <td>2024-06-12 06:36 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1234_US_G</td>
      <td>0</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>2</th>
      <td>15031984_AliSaeed</td>
      <td>0</td>
      <td>2024-09-01 02:31 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>3</th>
      <td>19980802_UmerSaeed</td>
      <td>30</td>
      <td>2024-09-01 02:32 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AS_123_US</td>
      <td>30</td>
      <td>2024-06-13 05:46 PM</td>
      <td>2024-06-13 05:46 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Babar_Azam</td>
      <td>30</td>
      <td>2024-09-01 02:19 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Cor_US</td>
      <td>46</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>7</th>
      <td>gmail</td>
      <td>0</td>
      <td>2024-06-13 05:24 AM</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>8</th>
      <td>g_AS</td>
      <td>0</td>
      <td>2024-06-13 05:18 AM</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>9</th>
      <td>g_US</td>
      <td>30</td>
      <td>2024-06-13 05:02 AM</td>
      <td>2024-06-13 05:01 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Hello_US</td>
      <td>1868</td>
      <td>2024-06-13 04:55 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Ijlal_Khan</td>
      <td>30</td>
      <td>2024-09-01 02:17 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Pakistan_1947-08-14</td>
      <td>0</td>
      <td>2024-09-01 02:30 PM</td>
      <td>2024-09-01 02:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Test</td>
      <td>30</td>
      <td>2024-06-22 11:30 PM</td>
      <td>2024-06-18 10:38 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Test1</td>
      <td>31</td>
      <td>2024-08-13 06:37 PM</td>
      <td>2024-08-11 10:53 AM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>15</th>
      <td>US1234</td>
      <td>1</td>
      <td>2024-06-13 04:46 PM</td>
      <td>2024-09-01 02:24 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>16</th>
      <td>US_123_AS</td>
      <td>30</td>
      <td>2024-06-13 05:46 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>17</th>
      <td>US_Test</td>
      <td>4201</td>
      <td>2024-06-13 05:53 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed</td>
    </tr>
    <tr>
      <th>18</th>
      <td>g</td>
      <td>0</td>
      <td>2024-08-13 07:30 PM</td>
      <td>2024-08-13 07:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\BH</td>
    </tr>
    <tr>
      <th>19</th>
      <td>a</td>
      <td>1868</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>20</th>
      <td>AS_1234_US</td>
      <td>30</td>
      <td>2024-08-11 03:54 PM</td>
      <td>2024-08-11 03:54 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>21</th>
      <td>b</td>
      <td>1</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-06-12 06:36 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>22</th>
      <td>c</td>
      <td>30</td>
      <td>2024-06-12 06:37 PM</td>
      <td>2024-06-12 06:35 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>23</th>
      <td>d</td>
      <td>1868</td>
      <td>2024-08-11 11:43 AM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Hello_t_US</td>
      <td>1868</td>
      <td>2024-08-11 03:32 PM</td>
      <td>2024-03-21 05:11 AM</td>
      <td>.csv</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>25</th>
      <td>US1234_Salam</td>
      <td>0</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-13 04:46 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>26</th>
      <td>US_123_AS_Hello</td>
      <td>30</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>27</th>
      <td>US_Test_Hi</td>
      <td>4201</td>
      <td>2024-08-11 03:15 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\DA</td>
    </tr>
    <tr>
      <th>28</th>
      <td>1234_US_G</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>29</th>
      <td>15031984_AliSaeed</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>30</th>
      <td>19980802_UmerSaeed</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:31 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Babar_Azam</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Cor_US</td>
      <td>46</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-13 05:02 AM</td>
      <td>.docx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>33</th>
      <td>gmail</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:24 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>34</th>
      <td>g_AS</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-06-13 05:18 AM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Ijlal_Khan</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-09-01 02:16 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Pakistan_1947-08-14</td>
      <td>0</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:30 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>37</th>
      <td>US1234</td>
      <td>1</td>
      <td>2024-09-01 03:31 PM</td>
      <td>2024-09-01 02:24 PM</td>
      <td>.txt</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>38</th>
      <td>US_123_AS</td>
      <td>30</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-13 05:45 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
    <tr>
      <th>39</th>
      <td>US_Test</td>
      <td>4201</td>
      <td>2024-09-01 03:32 PM</td>
      <td>2024-06-10 12:20 PM</td>
      <td>.xlsx</td>
      <td>D:/Copy/Umer_Saeed\Umer</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
