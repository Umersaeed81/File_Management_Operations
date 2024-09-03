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

# Advanced File Filtering and Management Techniques
![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Advanced_File_Filtering_and_Management_Techniques.png?raw=true)

In the realm of data management and file processing, the ability to efficiently filter and manage files is crucial. As datasets and file collections grow, the need to identify and work with specific files based on various criteria becomes increasingly important. This chapter delves into advanced techniques for filtering and managing files, focusing on methods that allow for precise control over file selection based on naming conventions, size, and content.

The first technique covered is file filtering by name patterns. This approach is particularly useful when dealing with large directories containing files with naming conventions that follow specific patterns. By using wildcard characters and pattern matching, you can easily locate files that fit predefined criteria. This is helpful in scenarios where files are categorized by project, date, or type, and you need to focus on only those that meet certain naming standards.

Next, we explore filtering files based on their size. This method is essential when managing disk space or ensuring that only files within a specific size range are processed. Whether you’re looking to exclude large files that could be cumbersome to handle or focus on smaller files that are more manageable, filtering by size allows for effective data management. This technique is often employed to avoid performance issues or to ensure that only relevant files are included in a dataset.

Combining multiple filtering criteria, such as name patterns and size restrictions, offers a more refined approach to file management. By applying both filters simultaneously, you can narrow down your file selection to those that precisely meet all specified conditions. This dual-layer filtering is useful for complex scenarios where files need to adhere to specific naming conventions and also fall within a certain size range, optimizing your data processing tasks.

Finally, the chapter introduces the use of regular expressions for more complex file filtering. Regular expressions provide a robust way to match filenames based on intricate patterns, including those that involve both numeric and alphabetic characters. This method is especially powerful when dealing with files that follow less straightforward naming conventions, enabling you to capture files that fit nuanced criteria that simple patterns might not cover.

Together, these techniques provide a comprehensive toolkit for advanced file management, allowing for greater flexibility and control over file processing tasks. By mastering these methods, you can enhance your ability to manage large volumes of data efficiently and effectively, tailored to your specific needs and requirements.

## 1. Listing All Files in a Directory

The code uses the glob function to list all files in the directory `D:/Copy/Umer_Saeed/`. It retrieves the paths of all files, regardless of their extensions, within the specified directory and stores them in the `df` variable as a list. This can be useful for tasks such as file management, batch processing, or analyzing the contents of a directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-01.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/*.*')
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv',
     'D:/Copy/Umer_Saeed\\1234_US_G.txt',
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt',
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx',
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx',
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx',
     'D:/Copy/Umer_Saeed\\Cor_US.docx',
     'D:/Copy/Umer_Saeed\\gmail.txt',
     'D:/Copy/Umer_Saeed\\g_AS.txt',
     'D:/Copy/Umer_Saeed\\g_US.xlsx',
     'D:/Copy/Umer_Saeed\\Hello_US.csv',
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx',
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt',
     'D:/Copy/Umer_Saeed\\Test.xlsx',
     'D:/Copy/Umer_Saeed\\Test1.xlsx',
     'D:/Copy/Umer_Saeed\\US1234.txt',
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx',
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']

## 2. Recursively Listing All Files in a Directory and Its Subdirectories

The code uses the glob function to recursively list all files within the directory `D:/Copy/Umer_Saeed/` and its subdirectories. By using the pattern `**/*.*` and setting `recursive=True`, the code retrieves the paths of all files, regardless of their extensions, from the main directory and all its nested subdirectories. This approach is helpful for comprehensive directory searches, batch processing, and tasks involving large directory structures with multiple layers.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-02.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/*.*',recursive=True)
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv',
    'D:/Copy/Umer_Saeed\\1234_US_G.txt',
    'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt',
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx',
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx',
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx',
     'D:/Copy/Umer_Saeed\\Cor_US.docx',
     'D:/Copy/Umer_Saeed\\gmail.txt',
     'D:/Copy/Umer_Saeed\\g_AS.txt',
     'D:/Copy/Umer_Saeed\\g_US.xlsx',
     'D:/Copy/Umer_Saeed\\Hello_US.csv',
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx',
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt',
     'D:/Copy/Umer_Saeed\\Test.xlsx',
     'D:/Copy/Umer_Saeed\\Test1.xlsx',
     'D:/Copy/Umer_Saeed\\US1234.txt',
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx',
     'D:/Copy/Umer_Saeed\\US_Test.xlsx',
     'D:/Copy/Umer_Saeed\\BH\\g.txt',
     'D:/Copy/Umer_Saeed\\DA\\a.csv',
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx',
     'D:/Copy/Umer_Saeed\\DA\\b.txt',
     'D:/Copy/Umer_Saeed\\DA\\c.xlsx',
     'D:/Copy/Umer_Saeed\\DA\\d.csv',
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv',
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt',
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx',
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx',
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt',
     'D:/Copy/Umer_Saeed\\Umer\\15031984_AliSaeed.txt',
     'D:/Copy/Umer_Saeed\\Umer\\19980802_UmerSaeed.xlsx',
     'D:/Copy/Umer_Saeed\\Umer\\Babar_Azam.xlsx',
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx',
     'D:/Copy/Umer_Saeed\\Umer\\gmail.txt',
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt',
     'D:/Copy/Umer_Saeed\\Umer\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx']

 
## 3. Listing Files in Subdirectories with Any Extension (Not Including Top-Level Directory)

**Search for Files:** Locate files within the specified source directory (`D:/Copy/Umer_Saeed/`) and its subdirectories.

**File Matching:** Include files with any extension (`*.*`).

**List of Files:** Return a list of all files from the subdirectories (but not from the specified directory itself) that match the pattern.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-03.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/*.*',recursive=False)
df
```
### Output

    ['D:/Copy/Umer_Saeed\\BH\\g.txt'
     'D:/Copy/Umer_Saeed\\DA\\a.csv'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\b.txt'
     'D:/Copy/Umer_Saeed\\DA\\c.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\d.csv'
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\Umer\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\Umer\\gmail.txt'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx']

## 4. Listing All CSV Files in a Directory

The code uses the `glob` function to retrieve all files with the `.csv` extension from the directory `D:/Copy/Umer_Saeed/`. By specifying the pattern `'*.csv'`, the code filters and lists only the CSV files located directly within the specified directory. This is useful for tasks such as processing or analyzing CSV files specifically in that directory

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-04.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/*.csv')
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv',
    'D:/Copy/Umer_Saeed\\Hello_US.csv']

## 5. Recursively Listing All CSV Files in a Directory and Its Subdirectories

The code uses the `glob` function to recursively list all files with a `.csv` extension within the directory `D:/Copy/Umer_Saeed/` and its subdirectories. By specifying the pattern `'**/*.csv'` and setting `recursive=True`, the code retrieves paths to all CSV files, including those located in any nested subdirectories. This is useful for comprehensive file searches and processing across multiple directory levels.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-05.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/*.csv',recursive=True)
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\DA\\a.csv'
     'D:/Copy/Umer_Saeed\\DA\\d.csv'
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv']
     
## 6. Filtering Files with Multiple Extensions from a Directory

The code filters and retrieves all files with specified extensions (`.xlsx` and `.txt`) from a given directory (`D:/Copy/Umer_Saeed/`). It uses a list of patterns and the `glob` function to search for files matching each pattern. The resulting list `df` contains the paths of all Excel and text files found directly in the specified source directory. This is useful for selectively processing files of different types within a single directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-06.png?raw=true)

```python
# import required libraries
from glob import glob
# source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# Define the required file extension 
patterns = ['*.xlsx', '*.txt']
# filter out required files
df = [file for pattern in patterns for file \
      in glob(f'{source_directory}{pattern}')]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt']

## 7. Recursively Filtering Files with Multiple Extensions from a Directory and Its Subdirectories

The code recursively searches for and retrieves all files with specified extensions (`.xlsx` and `.txt`) from a given directory (`D:/Copy/Umer_Saeed/`) and its subdirectories. By combining a list of patterns with the `glob` function and setting `recursive=True`, the code collects the paths of all Excel and text files found across the directory and its nested subdirectories. This approach is useful for batch processing, file management, or analysis tasks that involve multiple file types across multiple directory levels.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-07.png?raw=true)

```python
# import required libraries
from glob import glob
# source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# Define the required file extension 
patterns = ['*.xlsx', '*.txt']
# filter out required files
df = [file for pattern in patterns for file \
      in glob(f'{source_directory}{pattern}',recursive=True)]
df
```

### Output

    ['D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\c.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\BH\\g.txt'
     'D:/Copy/Umer_Saeed\\DA\\b.txt'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\Umer\\gmail.txt'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt']

## 8. Listing All Files with a Specific Prefix from a Directory

The code uses the `glob` function to list all files in the directory `D:/Copy/Umer_Saeed/` that have filenames starting with the prefix `US`. By specifying the pattern `'US*.*'`, the code retrieves paths of all files whose names begin with "US" and have any file extension. This is useful for filtering files based on a naming convention or specific prefix for further processing or analysis.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-08.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/US*.*')
df
```

### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']

## 9. Recursively Listing All Files with a Specific Prefix from a Directory and Its Subdirectories

The code uses the `glob` function to recursively search for and retrieve all files in the directory `D:/Copy/Umer_Saeed/` and its subdirectories that have filenames starting with the prefix US. By specifying the pattern `'**/US*.*'` and setting `recursive=True`, the code collects the paths of all files beginning with "US" across multiple directory levels, regardless of their file extensions. This is useful for filtering and processing files based on a specific naming pattern across a complex directory structure.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-09.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/US*.*',recursive=True)
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx']
 
## 10. Listing All Files with a Specific Suffix from a Directory

The code uses the `glob` function to list all files in the directory `D:/Copy/Umer_Saeed/` that have filenames ending with the suffix `US` and any file extension. By specifying the pattern `'*US.*'`, the code retrieves paths of all files whose names end with "US" directly within the specified directory. This is useful for filtering files based on a specific suffix in their names for tasks such as file management, processing, or analysis.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-10.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/*US.*')
df
```

### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv']

## 11. Recursively Listing All Files with a Specific Suffix from a Directory and Its Subdirectories

The code uses the `glob` function to recursively search for and retrieve all files within the directory `D:/Copy/Umer_Saeed/` and its subdirectories that have filenames ending with the suffix `US` and any file extension. By specifying the pattern `'**/*US.*'` and setting recursive=True, the code collects the paths of all files that meet this suffix criterion across multiple directory levels. This is useful for identifying and processing files based on a specific suffix within a complex directory structure.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-11.png)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/*US.*',recursive=True)
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx']

## 12. Listing All Files Containing a Specific Keyword in Their Name from a Directory 

The code uses the `glob` function to list all files in the directory `D:/Copy/Umer_Saeed/` that have filenames containing the keyword `US` and any file extension. By specifying the pattern `'*US*.*'`, the code retrieves the paths of all files where `US` appears anywhere in the filename. This is useful for filtering and managing files based on the presence of a specific keyword in their names.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-12.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/*US*.*')
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']
 
## 13. Recursively Listing All Files Containing a Specific Keyword in Their Name from a Directory and Its Subdirectories

The code uses the `glob` function to recursively search for and retrieve all files within the directory `D:/Copy/Umer_Saeed/` and its subdirectories that have filenames containing the keyword US and any file extension. By specifying the pattern `'**/*US*.*'` and setting `recursive=True`, the code collects the paths of all files that include the keyword US anywhere in their names, across multiple directory levels. This is useful for identifying and processing files based on a specific keyword within a complex directory structure.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-13.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/*US*.*',recursive=True)
df
```

### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx']


## 14. Listing All Text Files with a Specific Prefix from a Directory

The code uses the `glob` function to list all text files (`.txt`) in the directory `D:/Copy/Umer_Saeed/` that have filenames starting with the prefix `US`. By specifying the pattern `'US*.txt'`, the code retrieves the paths of all text files that begin with "US" in their names. This is useful for filtering and managing text files based on a specific prefix within a given directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-14.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/US*.txt')
df
```

### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt']

## 15. Recursively Listing All Text Files with a Specific Prefix from a Directory and Its Subdirectories

The code uses the `glob` function to recursively search for and retrieve all text files (`.txt`) within the directory `D:/Copy/Umer_Saeed/` and its subdirectories that have filenames starting with the prefix US. By specifying the pattern `'**/US*.txt'` and setting `recursive=True`, the code collects the paths of all matching text files across multiple directory levels. This approach is useful for locating and managing text files with a specific prefix throughout a complex directory structure.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-15.png?raw=true)

```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/US*.txt',recursive=True)
df
```

### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt']

## 16. Listing All Excel Files with a Specific Suffix from a Directory

The code uses the `glob` function to list all Excel files (`.xlsx`) in the directory `D:/Copy/Umer_Saeed/` that have filenames ending with the suffix `US`. By specifying the pattern `'*US.xlsx'`, the code retrieves the paths of all Excel files whose names end with "US" in the specified directory. This is useful for filtering and managing Excel files based on a specific suffix within a given directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-16.png?raw=true)
```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/*US.xlsx')
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx', <br>
    'D:/Copy/Umer_Saeed\\g_US.xlsx']

## 17. Recursively Listing All Excel Files with a Specific Suffix from a Directory and Its Subdirectories 

The code uses the `glob` function to recursively search for and retrieve all Excel files (`.xlsx`) within the directory `D:/Copy/Umer_Saeed/` and its subdirectories that have filenames ending with the suffix `US`. By specifying the pattern `'**/*US.xlsx'` and setting `recursive=True`, the code collects the paths of all matching Excel files across multiple directory levels. This is useful for locating and managing Excel files with a specific suffix within a complex directory structure.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-17.png?raw=true)
```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/*US.xlsx',recursive=True)
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx']

## 18. Listing All Excel Files Containing a Specific Keyword in Their Name from a Directory

The code uses the `glob` function to list all Excel files (`.xlsx`) in the directory `D:/Copy/Umer_Saeed/` that contain the keyword `US` anywhere in their filenames. By specifying the pattern `'*US*.xlsx'`, the code retrieves the paths of all Excel files that include "US" in their names. This is useful for filtering and managing Excel files based on the presence of a specific keyword within a given directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-18.png?raw=true)
```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/*US*.xlsx')
df
```

### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']
     
## 19. Recursively Listing All Excel Files Containing a Specific Keyword in Their Name from a Directory and Its Subdirectories

The code uses the `glob` function to recursively search for and retrieve all Excel files (`.xlsx`) within the directory `D:/Copy/Umer_Saeed/` and its subdirectories that have filenames containing the keyword `US`. By specifying the pattern `'**/*US*.xlsx'` and setting `recursive=True`, the code collects the paths of all matching Excel files across multiple directory levels. This approach is useful for locating and managing Excel files based on a specific keyword within a complex directory structure.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-19.png?raw=true)
```python
# import required libraries
from glob import glob
# filter out required files
df = glob('D:/Copy/Umer_Saeed/**/*US*.xlsx',recursive=True)
df
```

### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx']
## 20. Filtering Files with Multiple Prefixes from a Directory

The code filters and retrieves files from the directory `D:/Copy/Umer_Saeed/` that start with either of the specified prefixes (`US` or `AS`). By using a list of patterns and the `glob` function, it collects paths of all files that match these prefix patterns. This approach allows for selective file management and processing based on multiple naming conventions within the given directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-20.png?raw=true)
```python
# import required libraries
from glob import glob
# source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# Define the file name patterns
patterns = ['US*.*', 'AS*.*']
# filter out required files
df = [file for pattern in patterns for file \
      in glob(f'{source_directory}/{pattern}')]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx']

## 21. Recursively Filtering Files with Multiple Prefixes from a Directory and Its Subdirectories

The code recursively searches for and retrieves files from the directory `D:/Copy/Umer_Saeed/` and its subdirectories that start with either of the specified prefixes (`US` or `AS`). By using a list of patterns and the `glob` function with `recursive=True`, it collects paths of all files matching these prefix patterns across multiple directory levels. This approach facilitates comprehensive file management and processing based on multiple naming conventions within a complex directory structure.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-21.png?raw=true)

```python
# import required libraries
from glob import glob
# source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# Define the file name patterns
patterns = ['US*.*', 'AS*.*']
# filter out required files
df = [file for pattern in patterns for file \
      in glob(f'{source_directory}/{pattern}',recursive=True)]
df
```

### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx']

## 22. Filtering Files with Multiple Suffixes from a Directory

The code filters and retrieves files from the directory `D:/Copy/Umer_Saeed/` that have filenames ending with the specified suffixes (`US` or `AS`). By using a list of suffix patterns with `glob`, it collects the paths of all files that match these suffix patterns. This approach allows for selective management and processing of files based on their suffixes within the given directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-22.png?raw=true)

```python
# import required libraries
from glob import glob
# source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# Define the file name patterns
patterns = ['*US.*', '*AS.*']
# filter out required files
df = [file for pattern in patterns for file \
      in glob(f'{source_directory}/{pattern}')]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']
## 23. Recursively Filtering Files with Multiple Suffixes from a Directory and Its Subdirectories

The code recursively searches for and retrieves files from the directory `D:/Copy/Umer_Saeed/` and its subdirectories that have filenames ending with the specified suffixes (`US` or `AS`). By using a list of suffix patterns with `glob` and setting `recursive=True`, it collects the paths of all files that match these suffix patterns across multiple directory levels. This approach enables comprehensive file management and processing based on specific suffixes within a complex directory structure.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-23.png?raw=true)

```python
# import required libraries
from glob import glob
# source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# Define the file name patterns
patterns = ['*US.*', '*AS.*']
# filter out required files
df = [file for pattern in patterns for file \
      in glob(f'{source_directory}/{pattern}',recursive=True)]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']

## 24. Filtering Files with Multiple Keywords from a Directory Using Glob and Removing Duplicates

The code filters and retrieves files from the directory `D:/Copy/Umer_Saeed/` that contain any of the specified keywords (`US` or `AS`) in their filenames. It uses the `glob` function to match files based on these keyword patterns and then removes any duplicate file paths by converting the results to a set. The final output is a list of unique file paths that contain the specified keywords. This approach is useful for managing and processing files with certain keywords in their names while ensuring that duplicates are eliminated.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-24.png?raw=true)

```python
# import required libraries
from glob import glob
# source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# Define the file name patterns
patterns = ['*US*.*', '*AS*.*']
# filter out required files
df = list(set(file for pattern in patterns for file \
              in glob(f'{source_directory}/{pattern}')))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']
## 25. Recursively Filtering Files with Multiple Keywords from a Directory and Its Subdirectories and Removing Duplicates

The code recursively searches for and retrieves files from the directory `D:/Copy/Umer_Saeed/` and its subdirectories that contain any of the specified keywords (`US` or `AS`) in their filenames. By using the `glob` function with `recursive=True`, it matches files based on these keyword patterns and then removes duplicates by converting the results to a set. The final output is a list of unique file paths that include the specified keywords, ensuring comprehensive file management across multiple directory levels while eliminating redundancy.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-25.png?raw=true)


```python
# import required libraries
from glob import glob
# source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# Define the file name patterns
patterns = ['*US*.*', '*AS*.*']
# filter out required files
df = list(set(file for pattern in patterns for file \
         in glob(f'{source_directory}/{pattern}',recursive=True)))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt']
 
## 26. Combining Multiple Prefixes and Extensions to Filter Files from a Directory

The code generates and applies multiple file name patterns based on different prefixes (`AS`, `US`) and file extensions (`.xlsx`, `.txt`) to filter files from the directory `D:/Copy/Umer_Saeed/`. It uses `itertools.product` to create all possible combinations of base patterns and extensions, and then `glob` to match files according to these patterns. The results are combined using `itertools.chain` and duplicates are removed by converting the results to a set. The final output is a list of unique file paths that match any of the specified prefix-extension combinations, enabling comprehensive file management based on multiple criteria.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-26.png?raw=true)

```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'

# Define the base patterns and extensions
base_patterns = ['AS*', 'US*']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set(chain.from_iterable(glob(pattern) for pattern in patterns)))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']

## 27. Recursively Filtering Files with Multiple Prefixes and Extensions from a Directory and Its Subdirectories

The code recursively searches for and retrieves files from the directory `D:/Copy/Umer_Saeed/` and its subdirectories that match various combinations of prefixes (`AS`, `US`) and file extensions (`.xlsx`, `.txt`). By generating all possible patterns with these prefixes and extensions, it uses `glob` to find files that match any of these patterns. The results are then combined using `itertools.chain`, and duplicates are removed by converting the results to a set. The final output is a list of unique file paths that meet the specified criteria, enabling comprehensive file management across multiple directory levels and criteria.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-27.png?raw=true)

```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'

# Define the base patterns and extensions
base_patterns = ['AS*', 'US*']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set(chain.from_iterable(glob(pattern,recursive=True) for pattern in patterns)))
df
```

### Output

    ['D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']

## 28. Filtering Files with Multiple Suffixes and Extensions from a Directory

The code filters and retrieves files from the directory `D:/Copy/Umer_Saeed/` based on different suffixes (`*AS`, `*US`) and file extensions (`.xlsx`, `.txt`). By generating patterns that combine these suffixes and extensions, it uses `glob` to match files according to these patterns. The results are then combined using `itertools.chain`, and duplicates are removed by converting the results to a set. The final output is a list of unique file paths that match any of the specified suffix-extension combinations, facilitating organized file management based on multiple criteria.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-28.png?raw=true)

```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'

# Define the base patterns and extensions
base_patterns = ['*AS', '*US']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set(chain.from_iterable(glob(pattern) for pattern in patterns)))
df
```

### Output

    ['D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx']
 
## 29. Recursively Filtering Files with Multiple Suffixes and Extensions from a Directory and Its Subdirectories

The code recursively searches for and retrieves files from the directory `D:/Copy/Umer_Saeed/` and its subdirectories that match a variety of suffixes (`*AS`, `*US`) and file extensions (`.xlsx`, `.txt`). By generating all possible patterns from these suffixes and extensions, it uses `glob` to find files that fit any of these patterns. The results are combined using `itertools.chain` to aggregate all matching files and duplicates are removed by converting the results to a set. The final output is a list of unique file paths that meet the specified suffix and extension criteria across multiple directory levels.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-29.png?raw=true)

```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'

# Define the base patterns and extensions
base_patterns = ['*AS', '*US']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set(chain.from_iterable(glob(pattern,recursive=True) for pattern in patterns)))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt']

## 30. Filtering Files with Multiple Keywords and Extensions from a Directory

The code filters and retrieves files from the directory `D:/Copy/Umer_Saeed/` based on various keyword patterns (`*AS*`, `*US*`) and file extensions (`.xlsx`, `.txt`). It generates all possible combinations of these keywords and extensions, then uses `glob` to find files matching any of these patterns. The results are combined using `itertools.chain` to aggregate all matching files, and duplicates are removed by converting the results to a set. The final output is a list of unique file paths that satisfy the specified keyword and extension criteria.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-30.png?raw=true)

```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'

# Define the base patterns and extensions
base_patterns = ['*AS*', '*US*']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set(chain.from_iterable(glob(pattern) for pattern in patterns)))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']
## 31. Recursively Filtering Files with Multiple Keywords and Extensions from a Directory and Its Subdirectories

The code recursively searches for and retrieves files from the directory `D:/Copy/Umer_Saeed/` and its subdirectories that match various keyword patterns (`*AS*`, `*US*`) and file extensions (`.xlsx`, `.txt`). By generating all possible combinations of these patterns and extensions, it uses `glob` to find files that fit any of these criteria. The results are combined using `itertools.chain` to aggregate all matching files, and duplicates are removed by converting the results to a set. The final output is a list of unique file paths that meet the specified keyword and extension criteria across multiple directory levels.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-31.png?raw=true)


```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'

# Define the base patterns and extensions
base_patterns = ['*AS*', '*US*']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set(chain.from_iterable(glob(pattern,recursive=True) for pattern in patterns)))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']
 
## 32. Filtering Files Based on Size from a Directory

The code filters files from the directory `D:/Copy/Umer_Saeed/` to include only those that are smaller than 500 KB. It uses `glob` to list all files in the directory and then applies a size check using `os.path.getsize` to filter out files exceeding the specified size limit. The final output is a list of file paths for files that are under 500 KB in size.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-32.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*.*') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']

## 33. Filtering Files Based on Size from a Directory and Its Subdirectories 

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to identify files smaller than 500 KB. It uses `glob` to find all files in the directory structure and `os.path.getsize` to check each file's size. The result is a list of file paths for files that are under 500 KB, allowing for targeted management or processing of smaller files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-33.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*.*',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\BH\\g.txt'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\b.txt'
     'D:/Copy/Umer_Saeed\\DA\\c.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\Umer\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\Umer\\gmail.txt'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']

## 34. Filtering Text Files Based on Size from a Directory

The code filters text files from the directory `D:/Copy/Umer_Saeed/` that end with the `.txt` extension and are smaller than 500 KB. It uses `glob` to search for all `.txt` files in the specified directory and then uses `os.path.getsize` to check the size of each file. The result is a list of text file paths that meet the specified size criteria, allowing for focused processing or analysis of smaller text files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-34.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*.txt') \
      if os.path.getsize(file) < 500 * 1024
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt']

## 35. Recursively Filtering Text Files Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to find text files that end with the `.txt` extension and are smaller than 500 KB. It uses glob with the `recursive=True` parameter to locate all `.txt` files within the directory and its subdirectories. Then, it uses `os.path.getsize` to filter files based on size. The result is a list of text file paths that are under 500 KB, allowing for selective management or processing of smaller text files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-35.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*.txt',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\BH\\g.txt'
     'D:/Copy/Umer_Saeed\\DA\\b.txt'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\Umer\\gmail.txt'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt']

## 36. Filtering Files with Multiple Extensions Based on Size from a Directory 

The code filters Excel (`*.xlsx`) and text (`*.txt`) files from the directory `D:/Copy/Umer_Saeed/` based on their size, selecting only those smaller than 500 KB. It uses `glob` to find files matching the specified extensions and `os.path.getsize` to check each file's size. The result is a list of file paths for Excel and text files that meet the size criteria, allowing for efficient management or further processing of smaller files with these extensions.


![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-36.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# Define the patterns
patterns = ['*.xlsx', '*.txt']
# filter out required files
df = [file for pattern in patterns for file  
      in glob(f'{source_directory}{pattern}') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt']

## 37. Recursively Filtering Files with Multiple Extensions Based on Size from a Directory and Its Subdirectories

The code recursively filters Excel (`*.xlsx`) and text (`*.txt`) files from the directory `D:/Copy/Umer_Saeed/` and all its subdirectories, selecting only those files smaller than 500 KB. It uses `glob` with the `recursive=True` parameter to locate files matching the specified extensions in the directory and its subdirectories. Then, `os.path.getsize` is used to filter files based on their size. The output is a list of file paths that meet these criteria, allowing for efficient management or further processing of smaller Excel and text files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-37.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# Define the patterns
patterns = ['*.xlsx', '*.txt']
# filter out required files
df = [file for pattern in patterns for file in \
      glob(f'{source_directory}{pattern}',recursive=True)\
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\c.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\BH\\g.txt'
     'D:/Copy/Umer_Saeed\\DA\\b.txt'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\Umer\\gmail.txt'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt']

## 38. Filtering Files with a Specific Prefix Based on Size from a Directory 

The code filters files with a specific prefix (e.g., files starting with 'US') from the directory `D:/Copy/Umer_Saeed/`, selecting only those that are smaller than 500 KB. It uses `glob` to locate files in the directory that match the specified prefix and any file extension. `os.path.getsize` is then used to check each file's size, ensuring only files under 500 KB are included. The result is a list of file paths that meet both the prefix and size criteria, allowing for focused management or processing of smaller files with the given prefix.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-38.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/US*.*') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt', <br>
    'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']

## 39. Recursively Filtering Files with a Specific Prefix Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to find files that start with a specific prefix (e.g., 'US') and are smaller than 500 KB. It uses `glob` with the `recursive=True` parameter to locate files matching the prefix and any file extension. `os.path.getsize` is then used to filter out files exceeding the 500 KB size limit. The output is a list of file paths that meet both the prefix and size criteria, allowing for targeted management or processing of smaller files with the specified prefix.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-39.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/US*.*',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']

## 40. Filtering Files with a Suffix Based on Size from a Directory

The code filters files in the directory `D:/Copy/Umer_Saeed/` that have a specific suffix (e.g., containing 'US') and are smaller than 500 KB. It uses `glob` to locate files matching the suffix pattern and `os.path.getsize` to check each file's size. The result is a list of file paths for files that meet both the suffix and size criteria, allowing for the focused management or processing of smaller files with the specified suffix.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-40.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*US.*') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx']

## 41. Recursively Filtering Files with a Suffix Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to find files with a specific suffix (e.g., containing 'US') that are smaller than 500 KB. It uses `glob` with the `recursive=True` parameter to locate files matching the suffix pattern and `os.path.getsize` to filter files based on their size. The result is a list of file paths for files that meet both the suffix and size criteria, allowing for targeted management or processing of smaller files with the specified suffix.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-41.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*US.*',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx']

## 42. Filtering Files with a Keyword in the Filename Based on Size from a Directory

The code filters files in the directory `D:/Copy/Umer_Saeed/` that contain a specific keyword (e.g., 'US') in their filenames and are smaller than 500 KB. It uses `glob` to locate files matching the keyword pattern and `os.path.getsize` to check each file's size. The result is a list of file paths for files that meet both the keyword and size criteria, allowing for targeted management or processing of smaller files with the specified keyword in their names.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-42.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*US*.*') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']

## 43. Recursively Filtering Files with a Keyword in the Filename Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to identify files that include a specific keyword (e.g., 'US') in their filenames and are smaller than 500 KB. It utilizes `glob` with the `recursive=True` parameter to find files matching the keyword pattern across all subdirectories. The `os.path.getsize` function is then used to filter these files based on their size. The resulting list contains file paths of files that meet both the keyword and size criteria, facilitating targeted management or processing of smaller files with the specified keyword.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-43.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*US*.*',recursive=True)\
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']
 
## 44. Filtering Files with Multiple Prefixes Based on Size from a Directory 

The code filters files in the directory `D:/Copy/Umer_Saeed/` that match multiple prefix patterns (e.g., `'US*`.' and `'AS.*'`) and are smaller than 500 KB. It uses `glob` to locate files that start with the specified prefixes. The `os.path.getsize` function is then used to filter these files based on their size, ensuring only files under 500 KB are included. The result is a list of file paths for files that meet both the prefix and size criteria, enabling efficient management or processing of smaller files with the specified prefixes.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-44.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# Define the File name pattern
patterns = ['US*.*', 'AS*.*']
# filter out required files
df = [file for pattern in patterns for file in glob(f'{source_directory}/{pattern}')\
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx']

## 45. Recursively Filtering Files with Multiple Prefixes Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to find files that match multiple prefix patterns (e.g., `'US*`.' and `'AS.*'`) and are smaller than 500 KB. It utilizes glob with `recursive=True` to locate files that start with the specified prefixes in all subdirectories. The `os.path.getsize` function is then used to filter these files based on their size, ensuring only files under 500 KB are included. The result is a list of file paths for files that meet both the prefix and size criteria, facilitating targeted management or processing of smaller files with the specified prefixes.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-45.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# Define the File name pattern
patterns = ['US*.*', 'AS*.*']
# filter out required files
df = [file for pattern in patterns for file in glob(f'{source_directory}/{pattern}',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx']

## 46. Filtering Files with Multiple Suffix Patterns Based on Size from a Directory

The code filters files in the directory `source_directory` based on multiple suffix patterns (e.g., `'US'` and `'AS'`) and their size. It uses `glob` to locate files that match the specified suffix patterns. The `os.path.getsize` function is then used to ensure that only files smaller than 500 KB are included. The result is a list of file paths for files that meet both the suffix and size criteria, enabling efficient management or processing of smaller files with the specified suffixes.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-46.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# Define the File name pattern
patterns = ['*US.*', '*AS.*']
# filter out required files
df = [file for pattern in patterns for file in glob(f'{source_directory}/{pattern}') 
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx', <br>
     'D:/Copy/Umer_Saeed\\Cor_US.docx', <br>
     'D:/Copy/Umer_Saeed\\g_US.xlsx', <br>
     'D:/Copy/Umer_Saeed\\g_AS.txt', <br>
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']
 
## 47. Recursively Filtering Files with Multiple Suffix Patterns Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to find files that match multiple suffix patterns (e.g., `'US'` and `'AS'`) and are smaller than 500 KB. It uses `glob` with `recursive=True` to locate files that fit the specified suffix patterns in all subdirectories. The `os.path.getsize` function is then used to filter these files based on their size, ensuring that only files under 500 KB are included. The result is a list of file paths for files that meet both the suffix and size criteria, facilitating targeted management or processing of smaller files with the specified suffixes.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-47.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# Define the File name pattern
patterns = ['*US.*', '*AS.*']
# filter out required files
df = [file for pattern in patterns for file in \
      glob(f'{source_directory}/{pattern}',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']
 
## 48. Filtering Files with Multiple Keyword Patterns Based on Size from a Directory

The code filters files in the directory `D:/Copy/Umer_Saeed/` based on multiple keyword patterns (e.g., `'US'` and `'AS'`) and their size. It uses `glob` to locate files that match the specified keyword patterns. The `os.path.getsize` function is then used to ensure that only files smaller than 500 KB are included. The resulting list contains file paths of files that meet both the keyword and size criteria, facilitating the management or processing of smaller files with the specified patterns.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-48.png?raw=true)


```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# Define the File name pattern
patterns = ['*US*.*', '*AS*.*']
# filter out required files
df = [file for pattern in patterns for file in \
      glob(f'{source_directory}/{pattern}') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']
 
## 49. Recursively Filtering Files with Multiple Keyword Patterns Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory source_directory and its subdirectories to identify files that match multiple keyword patterns (e.g., `'US'` and `'AS'`) and are smaller than 500 KB. It uses glob with `recursive=True` to locate files that fit the specified keyword patterns across all subdirectories. The `os.path.getsize` function is then used to filter these files based on their size, ensuring that only files under 500 KB are included. The resulting list contains file paths of files that meet both the keyword and size criteria, enabling targeted management or processing of smaller files with the specified keywords.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-49.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# Define the File name pattern
patterns = ['*US*.*', '*AS*.*']
# filter out required files
df = [file for pattern in patterns for file in \
      glob(f'{source_directory}/{pattern}',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']

## 50. Filtering Text Files with Specific Prefix Based on Size from a Directory 

The code filters text files in the directory `D:/Copy/Umer_Saeed/` that start with the prefix `'US'` and have a `.txt` extension, ensuring that only those smaller than 500 KB are included. It uses glob to locate files matching the prefix and extension criteria, and `os.path.getsize` to filter these files based on their size. The result is a list of file paths for text files with the specified prefix that are under 500 KB, facilitating the management or processing of these smaller files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-50.png?raw=true)

```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/US*.txt') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt]

## 51. Recursively Filtering Text Files with Specific Prefix Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to identify text files that start with the prefix `'US'`. It filters these files to include only those that are smaller than 500 KB. The `glob` function with `recursive=True` is used to locate files matching the prefix and extension criteria throughout all subdirectories. The `os.path.getsize` function is then employed to filter out files based on their size, resulting in a list of file paths for text files with the specified prefix that are under 500 KB. This allows for focused management or processing of smaller text files that meet the given criteria.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-51.png?raw=true)


```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/US*.txt',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt']
 
## 52. Filtering Excel Files with Specific Prefix Based on Size from a Directory

The code filters Excel files in the directory `D:/Copy/Umer_Saeed/` that start with the prefix `'US'` and have an `.xlsx` extension, ensuring that only those smaller than 500 KB are included. It uses the `glob` function to locate files matching the prefix and extension criteria. The `os.path.getsize` function then filters these files based on their size. The result is a list of file paths for Excel files with the specified prefix that are under 500 KB, enabling targeted management or processing of these smaller files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-52.png?raw=true)


```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*US.xlsx') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx', <br>
    'D:/Copy/Umer_Saeed\\g_US.xlsx']

## 53. Recursively Filtering Excel Files with Specific Prefix Based on Size from a Directory and Its Subdirectories

The code recursively searches through the directory `D:/Copy/Umer_Saeed/` and its subdirectories to find Excel files that start with the prefix `'US'` and have the `.xlsx` extension. It filters these files to include only those that are smaller than 500 KB. The `glob` function with `recursive=True` locates files matching the criteria throughout all subdirectories, while the `os.path.getsize` function ensures that only files under 500 KB are selected. The final output is a list of file paths for Excel files with the specified prefix that meet the size requirement, facilitating focused management or processing of these files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-53.png?raw=true)


```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*US.xlsx',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx']

## 54. Filtering Excel Files Containing Keyword in Filename Based on Size from a Directory

The code searches the directory `D:/Copy/Umer_Saeed/` for Excel files where the filename contains the keyword `'US'` and has the `.xlsx` extension. It filters these files to include only those that are smaller than 500 KB. The `glob` function is used to match files with the specified pattern, and the `os.path.getsize` function ensures that only files under 500 KB are selected. The final result is a list of file paths for Excel files containing 'US' in their filenames that meet the size criteria, enabling targeted management or processing of these smaller files.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-54.png?raw=true)


```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*US*.xlsx') \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']

## 55. Filtering Excel Files with Keyword in Filename and Size Constraint from Subdirectories

The code searches through the specified directory `D:/Copy/Umer_Saeed/` and its subdirectories for Excel files whose filenames contain the keyword `'US'` and have the `.xlsx` extension. It further filters these files to include only those that are smaller than 500 KB. The glob function with `recursive=True` is used to match files according to the pattern in the specified directory and its subdirectories. The `os.path.getsize` function is used to filter out files that exceed the size limit, ensuring that only smaller files are included in the final list.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-55.png?raw=true)


```python
# import required libraries
import os
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*US*.xlsx',recursive=True) \
      if os.path.getsize(file) < 500 * 1024]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']
 
## 56. Filtering Files with Multiple Prefixes and Extensions Based on Size Constraint

The code filters files within the directory `D:/Copy/Umer_Saeed/` based on a combination of specified prefixes (`AS*`, `US*`) and file extensions (`.xlsx`, `.txt`). It generates patterns for all combinations of these prefixes and extensions, then searches for matching files. The resulting list is further filtered to include only those files that are smaller than 500 KB. The `glob` function is used to find files matching the patterns, and `os.path.getsize` is used to enforce the size constraint. The final output is a unique list of files that meet these criteria.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-56.png?raw=true)


```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'

# Define the base patterns and extensions
base_patterns = ['AS*', 'US*']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

df = list(set([
    file for pattern in patterns
    for file in glob(pattern)
    if os.path.getsize(file) < 500 * 1024]))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx']
 
## 57. Filtering Files Based on Multiple Prefixes and Extensions with Size Constraint from Directories and Subdirectories

The code filters files from the `D:/Copy/Umer_Saeed/` directory and its subdirectories based on specified prefixes (`AS*`, `US*`) and file extensions (`.xlsx`, `.txt`). It generates a list of file search patterns using all combinations of these prefixes and extensions. The `glob` function is used to locate files matching these patterns recursively within subdirectories. The files are then filtered to include only those that are smaller than 500 KB. The result is a unique list of file paths that meet these criteria.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-57.png?raw=true)


```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'

# Define the base patterns and extensions
base_patterns = ['AS*', 'US*']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set([
    file for pattern in patterns
    for file in glob(pattern,recursive=True)
    if os.path.getsize(file) < 500 * 1024]))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt']
     
## 58. Filtering Files Based on Suffix and Size from a Directory Using Multiple Patterns

The objective of this code is to:

**1. Define Base Patterns and Extensions:** Specify patterns that match filenames ending with certain suffixes (`*AS` and `*US`) and extensions (`.xlsx` and `.txt`).

**2. Generate File Patterns:** Create a list of file path patterns by combining the base patterns with the extensions.

**3. Filter Files by Size:** Search for files in the source directory that match these patterns, check their sizes, and include only those files smaller than 500 KB.

**4. Remove Duplicates:** Collect these files into a unique list, ensuring no duplicate file paths are included.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-58.png?raw=true)


```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'

# Define the base patterns and extensions
base_patterns = ['*AS', '*US']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set([
    file for pattern in patterns
    for file in glob(pattern)
    if os.path.getsize(file) < 500 * 1024]))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx']
 
## 59. Filtering Files by Suffix and Extension Based on Size in Directories and Subdirectories

The code filters files from a specified source directory and its subdirectories based on their suffix and file extension. It retrieves files that match any of the defined suffix patterns (`*AS` or `*US`) and extensions (`.xlsx` or `.txt`). Additionally, it checks that the file size is less than 500 KB. The resulting list contains unique file paths for files that meet all the specified criteria.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-59.png?raw=true)


```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'

# Define the base patterns and extensions
base_patterns = ['*AS', '*US']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set([
    file for pattern in patterns
    for file in glob(pattern,recursive=True)
    if os.path.getsize(file) < 500 * 1024]))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt']
 
## 60. Filtering Files by Multiple Keywords and Extensions Based on Size

The code aims to filter and list files from a specified directory (`D:/Copy/Umer_Saeed/`) based on a combination of multiple keywords and file extensions. It looks for files that match patterns involving keywords (`*AS*`, `*US*`) and extensions (`.xlsx`, `.txt`). It then checks each file's size and includes only those files that are smaller than 500 KB in the final list. The search is performed within the specified directory but does not include subdirectories.



![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-60.png?raw=true)


```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'

# Define the base patterns and extensions
base_patterns = ['*AS*', '*US*']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set([
    file for pattern in patterns
    for file in glob(pattern)
    if os.path.getsize(file) < 500 * 1024]))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx']

## 61. Filtering Files Based on Multiple Keywords and Extensions from Directory and Subdirectories, Limited by Size

This code generates a list of file paths by combining specified base patterns and extensions, and then filters the files based on their size. The steps are as follows:

1. **Define Source Directory**: Specifies the base directory where the search will be performed, including all its subdirectories.

2. **Set Patterns and Extensions**: Defines patterns for filenames and file extensions to be combined.

3. **Generate File Patterns**: Creates a list of search patterns by combining base patterns and file extensions.

4. **Filter Files**: Searches for files matching the generated patterns recursively within the source directory, and filters out files whose size is less than 500 KB.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-61.png?raw=true)


```python
# import required libraries
from glob import glob
from itertools import product, chain

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'

# Define the base patterns and extensions
base_patterns = ['*AS*', '*US*']
extensions = ['.xlsx', '.txt']

# Generate all combinations of base patterns with extensions
patterns = [f'{source_directory}{base_pattern}{extension}' \
            for base_pattern, extension in product(base_patterns, extensions)]

# filter out required files
df = list(set([
    file for pattern in patterns
    for file in glob(pattern,recursive=True)
    if os.path.getsize(file) < 500 * 1024]))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\1234_US_G.txt', <br>
     'D:/Copy/Umer_Saeed\\g_AS.txt', <br>
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt', <br>
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx', <br>
     'D:/Copy/Umer_Saeed\\US1234.txt', <br>
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx', <br>
     'D:/Copy/Umer_Saeed\\g_US.xlsx', <br>
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt', <br>
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt', <br>
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx', <br>
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx', <br>
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx', <br>
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt']

## 62. Filtering Files with Numeric Characters in Filenames from a Directory 

The objective of this code is to filter and list all files from the specified directory (`D:/Copy/Umer_Saeed/`) whose filenames contain at least one numeric character (0-9) using the `glob` function. The resulting list `df` will contain the paths of all such files that match the pattern.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-62.png?raw=true)

```python
# import required libraries
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*[0-9]*.*')]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']

## 63. Filtering Files from Directory and Subdirectories Based on Numeric Characters in Filenames

The code aims to search for files in a specified source directory (`D:/Copy/Umer_Saeed/`) and all its subdirectories that have filenames containing numeric characters (0-9). It uses the `glob` function with a wildcard pattern (`*[0-9]*.*`) to match any files where the filename contains at least one numeric character. The `recursive=True` option allows the search to include all subdirectories within the specified source directory. The matched files are then stored in the list `df`.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-63.png?raw=true)

```python
# import required libraries
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'
# filter out required files
df = [file for file in glob(f'{source_directory}/*[0-9]*.*',recursive=True)]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\Umer\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']
 
## 64. Filtering Files Without Digits in Filenames from a Directory

The objective of this code is to filter and list all files in the specified directory (`'D:/Copy/Umer_Saeed/'`) that do not contain any digits in their filenames. It uses the `glob` function to retrieve all files and then applies a regular expression (`re.search(r'\d', file)`) to exclude files that have digits in their names. The resulting list (`df`) contains only files without any numeric characters in their filenames.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-64.png?raw=true)

```python
# import required libraries
import re
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# filter out required files
df = [file for file in glob(f'{source_directory}')\
      if not re.search(r'\d', file)]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']
 
## 65. Filter Files Without Digits in Filenames from Directory and Subdirectories

The objective of this code is to retrieve all files from a specified directory and its subdirectories that do not contain any digits in their filenames. The code uses the `glob` function with the `recursive=True` parameter to search for files recursively, and the `re.search()` function to exclude files with any numeric characters in their names. The resulting list `df` contains only the files without digits in their filenames.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-65.png?raw=true)

```python
# import required libraries
import re
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/*.*'

# filter out required files
df = [file for file in glob(f'{source_directory}',recursive=True) \
      if not re.search(r'\d', file)]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed\\BH\\g.txt'
     'D:/Copy/Umer_Saeed\\DA\\a.csv'
     'D:/Copy/Umer_Saeed\\DA\\b.txt'
     'D:/Copy/Umer_Saeed\\DA\\c.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\d.csv'
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv'
     'D:/Copy/Umer_Saeed\\DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\Umer\\gmail.txt'
     'D:/Copy/Umer_Saeed\\Umer\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\US_Test.xlsx']

## 66. Filtering Files Containing Both Digits and Letters in Their Names from a Directory

The code filters files from a specified directory that contain both digits and letters in their filenames. It constructs a list of file paths by using the `glob` module to match all files in the directory with any extension. It then applies a filter to include only those files whose names contain at least one digit and one letter.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-66.png?raw=true)

```python
# import required libraries
import re
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'
# filter out required files
df = [file for file in glob(f'{source_directory}') if re.search(r'[0-9]', file) and re.search(r'[A-Za-z]', file)]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']
     
## 67. Filtering Files Containing Both Digits and Letters from Directory and Subdirectories

This code searches for files within the specified source directory and all its subdirectories that have filenames containing both digits and letters. It uses the `glob` module to recursively search through directories and the `re` module to apply regular expressions for filtering filenames based on their content.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-67.png?raw=true)

```python
# import required libraries
import re
from glob import glob
# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/*.*'
# filter out required files
df = [file for file in glob(f'{source_directory}',recursive=True) \
      if re.search(r'[0-9]', file) and re.search(r'[A-Za-z]', file)]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed\\DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed\\DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\Umer\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\Umer\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US1234.txt'
     'D:/Copy/Umer_Saeed\\Umer\\US_123_AS.xlsx']
 
## 68. Filter Files Based on Creation Date

List files created within the last 5 days

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-68.png?raw=true)

```python
# import required libraries
import os
from glob import glob
from datetime import datetime, timedelta

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# Filter files based on creation time
df = [file for file in glob(f'{source_directory}')
    if datetime.fromtimestamp(os.path.getctime(file)) > datetime.now() - timedelta(days=5)]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt']
 
## 69. Filter Files Based on File Creation Date Range

This example filters files created within a specified date range.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-69.png?raw=true)

```python
# import required libraries
import os
from glob import glob
from datetime import datetime

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# Define the date range
start_date = datetime(2024, 8, 1)
end_date = datetime(2024, 9, 30)

# Filter files based on creation date
df = [file for file in glob(f'{source_directory}')
    if start_date <= datetime.fromtimestamp(os.path.getctime(file)) <= end_date]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Test1.xlsx']
 
## 70. Filter Files Modified in the Last 24 Hours

List all files modified within the last 24 hours.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-70.png?raw=true)

```python
# Import required libraries
import os
from glob import glob
from datetime import datetime, timedelta

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# Filter files based on modification time within the specified hours
df = [file for file in glob(f'{source_directory}')
    if datetime.fromtimestamp(os.path.getmtime(file)) > datetime.now() - timedelta(hours=24)]
df
```
### Output

    []

```python
# Import required libraries
import os
from glob import glob
from datetime import datetime, timedelta

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# Filter files based on modification date within the last 1 days (only date difference)
df = [file for file in glob(f'{source_directory}')
    if datetime.fromtimestamp(os.path.getmtime(file)).date() >= (datetime.now() - timedelta(days=1)).date()]
df
```
### Output

    []
## 71. Filter Files by Date in Filename

List all files where the filename contains a date in the format YYYY-MM-DD

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-71.png?raw=true)

```python
# import required libraries
import re
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/**/'

# Define a regex pattern to match filenames containing a date
date_pattern = re.compile(r'\d{4}-\d{2}-\d{2}')

# Filter files based on regex pattern
df = [file for file in glob(f'{source_directory}/*.*', recursive=True)
    if date_pattern.search(os.path.basename(file))]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Umer\\Pakistan_1947-08-14.txt']
 
## 72. Filtering Files by Date Pattern in Filenames Using Regex

List all files where the filename contains a date in the format YYYYMMDD.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-72.png?raw=true)

```python
# import required libraries
import re
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# Define a regex pattern to match filenames containing a date in YYYYMMDD format
date_pattern = re.compile(r'\d{8}')  # Matches 8 consecutive digits

# Filter files based on regex pattern
df = [file for file in glob(f'{source_directory}')
    if date_pattern.search(os.path.basename(file))]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx']
 
## 73. Filter Files Based on Size Range

List all files within a specific size range (e.g., between 20 KB and 50 KB).

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-73.png?raw=true)

```python
# import required libraries
import os
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# Define the size range
min_size = 20 * 1024   # 20 KB
max_size = 50 * 1024   # 50 KB

# Filter files based on size range
df = [file for file in glob(f'{source_directory}')
    if min_size < os.path.getsize(file) < max_size]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx']
 
## 74. Filter Files Based on File Name Length (Excluding File Extension)

Filter files in the source directory to include only those with filenames (excluding extensions) that are 15 characters or fewer in length.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-74.png?raw=true)

```python
# import required libraries
import os
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# Define the maximum filename length
max_length = 15

# Filter files based on filename length without extension
df = [file for file in glob(f'{source_directory}')
    if len(os.path.splitext(os.path.basename(file))[0]) <= max_length]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']
 
## 75. Filter Files Based on File Name Length (Including File Extension)

Filter files in the source directory to include only those with filenames that are 20 characters or fewer in length.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-75.png?raw=true)

```python
# import required libraries
import os
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/*.*'

# Filter files based on filename length
df = [file for file in glob(f'{source_directory}')
    if len(os.path.basename(file)) <= 20]
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx']
 
## 76. Filter Files Based on Specific Subdirectory Names

Filter files from specific subdirectories (`DA` and `BH`) within the source directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-76.png?raw=true)

```python
# import required libraries
import os
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'

# Define the subdirectory names to filter
subdirectories = ['DA', 'BH']

# Filter files based on subdirectory names
df = [file for subdir in subdirectories
    for file in glob(f'{source_directory}/{subdir}/*.*', recursive=True)]
df
```
### Output

    ['D:/Copy/Umer_Saeed//DA\\a.csv'
     'D:/Copy/Umer_Saeed//DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed//DA\\b.txt'
     'D:/Copy/Umer_Saeed//DA\\c.xlsx'
     'D:/Copy/Umer_Saeed//DA\\d.csv'
     'D:/Copy/Umer_Saeed//DA\\Hello_t_US.csv'
     'D:/Copy/Umer_Saeed//DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed//DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed//DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed//BH\\g.txt']
 
## 77. Filtering Files from a Source Directory and Specified Subdirectories

Collect files from the source directory and specific subdirectories (`DA` and `BH`).

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-77.png?raw=true)

```python
# import required libraries
import os
from glob import glob

# Source directory
source_directory = 'D:/Copy/Umer_Saeed/'

# Define the subdirectory names to filter
subdirectories = ['DA', 'BH']

# Include files from the source_directory and the specified subdirectories only
df = []

# Include files from the source_directory
df.extend(glob(f'{source_directory}/*.*'))

# Include files from the specified subdirectories
for subdir in subdirectories:
    df.extend(glob(f'{source_directory}{subdir}/*.*'))
df
```
### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv'
     'D:/Copy/Umer_Saeed\\1234_US_G.txt'
     'D:/Copy/Umer_Saeed\\15031984_AliSaeed.txt'
     'D:/Copy/Umer_Saeed\\19980802_UmerSaeed.xlsx'
     'D:/Copy/Umer_Saeed\\AS_123_US.xlsx'
     'D:/Copy/Umer_Saeed\\Babar_Azam.xlsx'
     'D:/Copy/Umer_Saeed\\Cor_US.docx'
     'D:/Copy/Umer_Saeed\\gmail.txt'
     'D:/Copy/Umer_Saeed\\g_AS.txt'
     'D:/Copy/Umer_Saeed\\g_US.xlsx'
     'D:/Copy/Umer_Saeed\\Hello_US.csv'
     'D:/Copy/Umer_Saeed\\Ijlal_Khan.xlsx'
     'D:/Copy/Umer_Saeed\\Pakistan_1947-08-14.txt'
     'D:/Copy/Umer_Saeed\\Test.xlsx'
     'D:/Copy/Umer_Saeed\\Test1.xlsx'
     'D:/Copy/Umer_Saeed\\US1234.txt'
     'D:/Copy/Umer_Saeed\\US_123_AS.xlsx'
     'D:/Copy/Umer_Saeed\\US_Test.xlsx'
     'D:/Copy/Umer_Saeed/DA\\a.csv'
     'D:/Copy/Umer_Saeed/DA\\AS_1234_US.xlsx'
     'D:/Copy/Umer_Saeed/DA\\b.txt'
     'D:/Copy/Umer_Saeed/DA\\c.xlsx'
     'D:/Copy/Umer_Saeed/DA\\d.csv'
     'D:/Copy/Umer_Saeed/DA\\Hello_t_US.csv'
     'D:/Copy/Umer_Saeed/DA\\US1234_Salam.txt'
     'D:/Copy/Umer_Saeed/DA\\US_123_AS_Hello.xlsx'
     'D:/Copy/Umer_Saeed/DA\\US_Test_Hi.xlsx'
     'D:/Copy/Umer_Saeed/BH\\g.txt']

## 78. Listing All CSV Files and Empty Directories in a Given Directory Recursively

The goal of this code is to find all CSV files and empty folders inside a specific directory and its subdirectories. The code searches through all levels of the directory, lists all CSV files, checks for empty folders, and combines the results into a single list

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Filtering/Example-78.png?raw=true)

```python
# import required libraries
import os
from glob import glob

# Get all files matching the pattern
files = glob('D:/Copy/Umer_Saeed/**/*.csv', recursive=True)

# Get all directories including empty ones
directories = []
for dirpath, dirnames, filenames in os.walk('D:/Copy/Umer_Saeed'):
    # Only include the directory if it is empty
    if not filenames and not dirnames:
        directories.append(dirpath)

# Combine both files and empty directories
df = sorted(files + directories)
df
```

### Output

    ['D:/Copy/Umer_Saeed\\03_PRS.csv',
     'D:/Copy/Umer_Saeed\\Corvit',
     'D:/Copy/Umer_Saeed\\DA\\Hello_t_US.csv',
     'D:/Copy/Umer_Saeed\\DA\\a.csv',
     'D:/Copy/Umer_Saeed\\DA\\d.csv',
     'D:/Copy/Umer_Saeed\\Hello_US.csv']


'''python
from glob import glob

# Define the list of paths to search
source_directory = ['D:/Copy/Umer_Saeed/**/*.csv', 'D:/Copy/Ali_Saeed/*.txt']

# Collect all files from the specified paths using list comprehension
df = [file for path in source_directory for file in glob(path,recursive=True)]

# Display the result
result
'''
 
![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true)
