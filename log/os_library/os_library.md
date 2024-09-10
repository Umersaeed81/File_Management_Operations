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

# Mastering File and Directory Management in Python

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/Mastering_File_and_Directory_Management_in_Python.png?raw=true)

Effective management of files and directories is essential for maintaining a well-organized and efficient computing environment. Before diving into the `os` library's functionalities, it's crucial to understand the foundational concepts of directories, subdirectories, and files, which form the building blocks of any file system.

## What is a Directory?

A **directory** (often referred to as a folder) is a container that holds files and other directories. It serves as a primary means of organizing and storing data, providing a structured way to categorize related files. Directories enable users to logically group files, making it easier to locate and manage them. For example, a directory named "Projects" might contain multiple files related to various ongoing projects, providing a single location to manage and access them efficiently.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/Directory.png?raw=true)

## Understanding Subdirectories

A **subdirectory** is a directory nested within another directory. Subdirectories offer a more granular level of organization, allowing users to further categorize data under specific themes or projects. For instance, within the "Projects" directory, you might have subdirectories like "Project_A" and "Project_B," each containing its own set of files. This hierarchical structure supports deeper organization, making it easier to maintain, navigate, and manage larger sets of data.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/Subdirectory.png?raw=true)

## What is a File?

A **file** is a basic unit of storage that contains data, such as text, images, code, or any other type of content. Files are the primary objects that directories and subdirectories are designed to manage. Each file is stored with a specific name and extension (e.g., `.txt`, `.jpg`, `.py`), which helps in identifying its type and purpose. Managing files involves operations like creating, reading, writing, deleting, and renaming, which are fundamental to any file management system.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/File.png?raw=true)

This chapter will guide you through the practical applications of the `os` library, demonstrating how to automate repetitive file operations, implement effective directory structures, and manage files with ease. Whether you are organizing datasets, managing configuration files, or maintaining backups, mastering the `os` library will enhance your ability to create a robust and organized file system.

# The Role of the `os` Library in Python

With a clear understanding of directories, subdirectories, and files, the next step is to explore how these can be managed programmatically using Python. The `os` **library** in Python is a powerful module that allows for seamless interaction with the operating system, providing a range of functions to manipulate files and directories. From creating and deleting directories to moving and renaming files, the `os` library enables developers to automate and optimize their file management workflows.

## Introduction to the `os` Library

The `os` library is an essential tool for Python developers and system administrators who need to handle file and directory operations efficiently. By leveraging its comprehensive functions, you can perform tasks such as:

## 1. Understanding the Operating System

When working with file and directory management in Python, it's crucial to have a basic understanding of the operating system on which your code is running. Different operating systems, such as Windows, macOS, and Linux, have their own file structures, path conventions, and system commands. This can affect how certain operations are performed, such as navigating directories, checking file paths, and managing file permissions. By understanding the underlying operating system, you can write more robust and adaptable code that works seamlessly across different environments.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/understanding_the%20os.png?raw=true)

## a). `os.name`

In Python, `os.name` provides a simple way to identify the platform or operating system on which the Python interpreter is currently running. The output `'nt'` indicates that the operating system is **Windows**.

Here is a breakdown of the possible values for `os.name`:

**1. `'nt'`:** Refers to Windows (from Windows NT family, including modern Windows versions).

**2. `'posix'`:** Refers to Unix-like operating systems (e.g., Linux, macOS).

**3. `'java'`:** Refers to the Java platform.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/Example-01.png?raw=true)

## Determining the Operating System

The objective of the code is to find out the name of the operating system that Python is running on. The code uses the `os` module to retrieve this information.


```python
import os
os.name
```

### Output

    'nt'



## Detecting and Printing the Operating System Platform

The objective of the code is to determine the type of operating system Python is running on and print a message accordingly. 
- If the system is Windows, it prints "Running on Windows."
- If it's a Unix-like system (such as Linux or macOS), it prints "Running on a Unix-like system."
- For any other or unknown platforms, it prints "Running on an unknown platform."


```python
import os

if os.name == 'nt':
    print("Running on Windows")
elif os.name == 'posix':
    print("Running on a Unix-like system")
else:
    print("Running on an unknown platform")
```
### Output
    Running on Windows
    

## 2. Navigating the File System

Navigating the file system is a fundamental aspect of managing files and directories in any programming environment. It involves moving between different directories, identifying the current location, and accessing specific files or folders. This is crucial for tasks such as reading from or writing to files, organizing data, and automating workflows. A solid grasp of how to navigate the file system allows you to interact efficiently with the operating system, making it easier to handle files and directories dynamically within your programs. Understanding these basic operations lays the foundation for more advanced file management techniques

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/navigating_the_file_system.png?raw=true)

Key `os` Functions for Navigating the File System are;

- `os.getcwd()`
- `os.chdir()`

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/Navigating_the_File_System.png?raw=true)

## a). `os.getcwd()`

The `os.getcwd()` function in Python is used to **get the current working directory** of a Python script or interpreter session. The "current working directory" is the folder from which the Python script is being run or where the interpreter is currently located.

Here is a summary of the key points about the `os.getcwd()` function and its usefulness:

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/get_the_current_working_directory.png?raw=true)

### Returns an Absolute Path 
`os.getcwd()` returns the absolute path of the current working directory, which includes the full directory path starting from the root of the filesystem.

### Useful for File Operations 
When you want to perform file operations, knowing the current working directory is crucial, especially when using relative paths.

### Does Not Change the Directory
It only returns the current directory path and does not change it. If you want to change the working directory, you would use `os.chdir()`.

### Building File Paths Dynamically
When you need to create or access files relative to the current working directory.

### Debugging
Helps to understand where the script is executing, especially when dealing with relative paths.

### Cross-Platform Compatibility
Useful for writing code that needs to run on different operating systems without hardcoding file paths.

## Retrieving the Current Working Directory

The objective of the code is to find and display the current working directory where Python is running. The code uses the os module to retrieve this directory path.


```python
import os
os.getcwd()
```

### Output

    'C:\\Users\\Pakistan\\File_handing_book'



## b). `os.chdir()`

In Python, the `os.chdir()` function is used to change the current working directory. The path you provide to `os.chdir()` can be specified in several ways, depending on the format and type of path you use. 

Below are different approaches to change the directory:

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_chdir.png?raw=true)

### Changing the Current Working Directory Using Forward Slashes

-  Forward slashes are universally accepted as path separators in Python, even on Windows systems. This approach is straightforward and avoids issues with escape sequences.
- The objective is to change the current working directory to `D:/os_library` using forward slashes and verify the change by printing the current directory before and after the change.


```python
import os

# Print the current working directory
print(f"Before Change: {os.getcwd()}")

# Change the current working directory to 'D:/OS_Library'
os.chdir('D:/os_library')  # Use forward slashes

# Verify the change using os.getcwd()
print(f"After Change: {os.getcwd()}")
```
### Output

    Before Change: C:\Users\Pakistan\File_handing_book
    After Change: D:\os_library
    

### Changing the Current Working Directory Using Double Forward Slashes

- Double forward slashes are sometimes used to separate directories. While this can work, it is less conventional and might cause unexpected behavior in some cases.
- The objective is to change the current working directory to `D://os_library` using double forward slashes and verify the change by printing the current directory before and after the change.


```python
import os

# Print the current working directory
print(f"Before Change: {os.getcwd()}")

# Change the current working directory to 'D://OS_Library'
os.chdir('D://os_library')  # Use double forward slashes

# Verify the change using os.getcwd()
print(f"After Change: {os.getcwd()}")
```
### Output

    Before Change: D:\os_library
    After Change: D:\os_library
    

### Changing the Current Working Directory Using a Raw String for Backslashes

-  On Windows, backslashes (`\`) are typically used as path separators. To avoid problems with escape characters, you can use raw strings by prefixing the string with r, which treats backslashes as literal characters.
- The objective is to change the current working directory to `D:\os_library` using a raw string to handle backslashes and verify the change by printing the current directory before and after the change.


```python
import os

# Print the current working directory
print(f"Before Change: {os.getcwd()}")

# Change the current working directory to 'D:\OS_Library'
os.chdir(r'D:\os_library')  # Use raw string to handle backslashes

# Verify the change using os.getcwd()
print(f"After Change: {os.getcwd()}")
```
### Output

    Before Change: D:\os_library
    After Change: D:\os_library
    

### Using Backslashes (`\`) without Raw Strings

- If you use backslashes in regular strings without specifying them as raw strings, you might encounter issues due to [escape sequences being interpreted by Python](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/Handling_Special_Characters_in_Strings_and_File_Paths.md).

## 3. Listing Directory Contents

Listing the contents of a directory is a fundamental operation that allows you to view all files and subdirectories within a specified location. This is essential for understanding the structure of the file system, locating specific files, and performing bulk operations, such as copying, moving, or deleting files. By listing directory contents, you can also gather information about file types, names, sizes, and modification dates, which is helpful for data analysis, cleanup tasks, and managing large collections of files. Effective directory listing is a key step in many automation and data management workflows.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/listing_contents.png?raw=true)

Key `os` Functions for Listing Directory Contents System are;

- `os.listdir()`
- `os.scandir()`

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/Listing_Directory_Contents.png?raw=true)

## a). `os.listdir()`

The `os.listdir()` function in Python is used to **list all files and directories** in a specified directory. If no directory is specified, it defaults to listing the contents of the current working directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/Example-02.png?raw=true)

- **Function Signature:** `os.listdir(path='.')`:
  - `path (optional):` The directory path you want to list. If omitted, it defaults to the current working directory `('.')`.

- **Return Value:** `os.listdir()` returns a list of names of the entries in the specified directory. This list includes both files and directories.

- The `os.curdir` is a constant in the `os` module that represents the current directory, denoted by `'.'`. When you use os.curdir as an argument in `os.listdir()`, it behaves the same as using `'.'` directly or omitting the argument altogether.

## Listing the Contents of the Current Directory

The objective of the code is to list all the files and folders in the current working directory using Python's `os` module. The code retrieves the names of the contents of the current directory and prints them to the screen.

### Method-1


```python
import os

# List files and directories in the current working directory
contents = os.listdir('.')
print("Current Directory Contents:")
print(contents)
```

### Output

    Current Directory Contents:
    ['AhmedSaeed', 'AliSaeed', 'Bilal_Iqbal.accdb', 'Ijlal_Khan', 'New Text Document.txt', 'New_version.xlsx', 'UmerSaeed']
    

### Method-2


```python
import os

# List files and directories in the current working directory
contents = os.listdir()
print("Current Directory Contents:")
print(contents)
```
### Output

    Current Directory Contents:
    ['AhmedSaeed', 'AliSaeed', 'Bilal_Iqbal.accdb', 'Ijlal_Khan', 'New Text Document.txt', 'New_version.xlsx', 'UmerSaeed']
    

### Method-3


```python
import os

# List files and directories in the current working directory
contents = os.listdir(os.curdir)
print("Current Directory Contents:")
print(contents)
```
### Output

    Current Directory Contents:
    ['AhmedSaeed', 'AliSaeed', 'Bilal_Iqbal.accdb', 'Ijlal_Khan', 'New Text Document.txt', 'New_version.xlsx', 'UmerSaeed']
    

## Listing the Contents of a Specific Directory

The objective of the code is to list all the files and folders in a specific directory (`D:/os_library`) using Python's `os` module. The code specifies the directory path, retrieves the names of the contents in that directory, and prints them to the screen.



```python
import os

# Specify the directory path
directory_path = 'D:/os_library'  

# List files and directories in the specified directory
contents = os.listdir(directory_path)
print(f"Contents of {directory_path}:")
print(contents)
```

### Output

    Contents of D:/os_library:
    ['AhmedSaeed', 'AliSaeed', 'Bilal_Iqbal.accdb', 'Ijlal_Khan', 'New Text Document.txt', 'New_version.xlsx', 'UmerSaeed']
    

## Handling Errors While Listing Directory Contents

The objective of the code is to safely attempt to list all files and folders in a specified directory using Python's `os` module. The code handles potential errors such as the directory not existing (`FileNotFoundError`) or insufficient permissions to access the directory (`PermissionError`). If the directory is accessible, it prints its contents; otherwise, it displays an appropriate error message.


```python
import os

directory_path = 'D:/os_library'  

try:
    # Attempt to list the directory contents
    contents = os.listdir(directory_path)
    print(f"Contents of {directory_path}:")
    print(contents)
except FileNotFoundError:
    print(f"Error: The directory '{directory_path}' does not exist.")
except PermissionError:
    print(f"Error: You do not have permission to access '{directory_path}'.")
```
### Output

    Contents of D:/os_library:
    ['AhmedSaeed', 'AliSaeed', 'Bilal_Iqbal.accdb', 'Ijlal_Khan', 'New Text Document.txt', 'New_version.xlsx', 'UmerSaeed']
    

## b). `os.scandir()`

- Used to iterate over the contents of a directory, providing detailed information about each entry (file, directory, or symbolic link).

- Returns `DirEntry` objects that have methods like `.is_file()`, `.is_dir()`, and `.is_symlink()` to check the type of each entry.

- Efficient and provides a way to access file or directory metadata without making separate system calls.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_scandir.png?raw=true)

## Exploring Directory Contents and Retrieving File Information

The objective of the code is to explore and print detailed information about the contents of a specified directory (`D://OS_Library`). Using `os.scandir`, it retrieves and displays the name, full path, type (file or directory), and symbolic link status of each entry. Additionally, it provides file size, last modified time, inode number, and filesystem path representation for each entry.


```python
import os
import time
# Specify the directory path
directory_path = 'D://OS_Library'

# Use os.scandir to get DirEntry objects
with os.scandir(directory_path) as entries:
    for entry in entries:
        print(f"Name: {entry.name}")  # Base name of the entry
        print(f"Path: {entry.path}")  # Full path of the entry
        print(f"Is File: {entry.is_file()}")  # Is it a file?
        print(f"Is Directory: {entry.is_dir()}")  # Is it a directory?
        print(f"Is Symlink: {entry.is_symlink()}")  # Is it a symbolic link?")
        
        # Get file status information
        stat_info = entry.stat()
        print(f"File size: {stat_info.st_size} bytes")
        print(f"Last modified: {time.ctime(stat_info.st_mtime)}")
        
        # Get inode number
        print(f"Inode number: {entry.inode()}")

        # File system path representation
        print(f"Filesystem path: {entry.__fspath__()}")
        print("-" * 40)
```
### Output

    Name: AhmedSaeed
    Path: D://OS_Library\AhmedSaeed
    Is File: False
    Is Directory: True
    Is Symlink: False
    File size: 0 bytes
    Last modified: Thu Sep  5 18:09:56 2024
    Inode number: 35465847065551877
    Filesystem path: D://OS_Library\AhmedSaeed
    ----------------------------------------
    Name: AliSaeed
    Path: D://OS_Library\AliSaeed
    Is File: False
    Is Directory: True
    Is Symlink: False
    File size: 0 bytes
    Last modified: Thu Sep  5 14:50:32 2024
    Inode number: 35747322042262534
    Filesystem path: D://OS_Library\AliSaeed
    ----------------------------------------
    Name: Bilal_Iqbal.accdb
    Path: D://OS_Library\Bilal_Iqbal.accdb
    Is File: True
    Is Directory: False
    Is Symlink: False
    File size: 495616 bytes
    Last modified: Thu Sep  5 14:49:34 2024
    Inode number: 36028797018973191
    Filesystem path: D://OS_Library\Bilal_Iqbal.accdb
    ----------------------------------------
    Name: Ijlal_Khan
    Path: D://OS_Library\Ijlal_Khan
    Is File: False
    Is Directory: True
    Is Symlink: False
    File size: 0 bytes
    Last modified: Thu Sep  5 20:04:24 2024
    Inode number: 35465847065551880
    Filesystem path: D://OS_Library\Ijlal_Khan
    ----------------------------------------
    Name: New Text Document.txt
    Path: D://OS_Library\New Text Document.txt
    Is File: True
    Is Directory: False
    Is Symlink: False
    File size: 0 bytes
    Last modified: Thu Sep  5 14:49:38 2024
    Inode number: 36591746972394506
    Filesystem path: D://OS_Library\New Text Document.txt
    ----------------------------------------
    Name: New_version.xlsx
    Path: D://OS_Library\New_version.xlsx
    Is File: True
    Is Directory: False
    Is Symlink: False
    File size: 30549 bytes
    Last modified: Sun Sep  8 11:39:37 2024
    Inode number: 36591746972394507
    Filesystem path: D://OS_Library\New_version.xlsx
    ----------------------------------------
    Name: UmerSaeed
    Path: D://OS_Library\UmerSaeed
    Is File: False
    Is Directory: True
    Is Symlink: False
    File size: 0 bytes
    Last modified: Thu Sep  5 20:13:37 2024
    Inode number: 36873221949105164
    Filesystem path: D://OS_Library\UmerSaeed
    ----------------------------------------
    

## 4. Checking Path Existence and Access

Checking path existence and access is a crucial step in file and directory management. It involves verifying whether a specified path exists, and if so, determining whether it is a file or directory. Additionally, this process ensures that your program has the necessary permissions to read from or write to the path. By confirming these aspects, you can prevent errors and handle exceptions gracefully, making your code more reliable and robust. This is particularly important in scenarios where the presence or type of files and directories impacts the functionality of your application or script.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/path_existence_and_access.png?raw=true)

Key `os` Functions are;

- `os.path.exists(path)`
- `os.path.isdir(path)`
- `os.path.isfile(path)`
- `os.access(path, mode)`

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_exists_isdir.png?raw=true)

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_isfile_access.png?raw=true)

## a). `os.path.exists(path)`

- Checks whether a specified path exists, **regardless of whether it is a file, directory, or symbolic link**.

- Returns `True` if the path exists and `False` otherwise.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_exists.png?raw=true)

## Checking Path Existence Using `os.path.exists()`

The objective of the code is to verify and display whether the specified directory and files exist at the given paths.

### Example


```python
import os
print(os.path.exists('D:\\os_library'))
```
### Output
    True
    

This example checks whether the directory `D:\os_library` exists. Since the output is `True`, it means that the directory `D:\os_library` is present in the file system.

### Example


```python
import os
print(os.path.exists('D:\\os_library\\Bilal_Iqbal.accdb'))
```
### Output
    True
    

This example checks if the file `Bilal_Iqbal.accdb` exists within the directory `D:\os_library`. The output is `True`, indicating that the file `Bilal_Iqbal.accdb` exists in the specified location.

### Example


```python
import os
print(os.path.exists('D:\\os_library\\Umer_Saeed.csv'))
```
### Output
    False
    

Here, it checks if the file `Umer_Saeed.csv` exists within the directory `D:\os_library`. The output is `False`, which means that there is no file named `Umer_Saeed.csv` in that directory.

### Example


```python
import os
print(os.path.exists('D:\\os_library1'))
```
### Output
    False
    

This example checks for the existence of a directory named `D:\os_library1`. The output is `False`, indicating that the directory `D:\os_library1` does not exist in the file system.

## b). `os.path.isdir(path)`

- Checks specifically whether a specified path exists **and is a directory**.

- Returns `True` if the path exists **and is a directory**, otherwise returns `False`.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_isdir.png?raw=true)

## Determining If a Path is a Directory Using `os.path.isdir()`

The objective of the code is to check and print whether the specified paths are directories.

### Example


```python
import os
print(os.path.isdir('D:\\os_library'))
```
### Output

    True
    

This example checks if the path `D:\os_library` is an existing directory. Since the output is `True`, it confirms that `D:\os_library` exists and is indeed a directory.

### Example


```python
import os
print(os.path.isdir('D:\\os_library1'))
```
### Output

    False
    

Here, it checks whether `D:\os_library1` is a directory. The output is `False`, indicating that `D:\os_library1` does not exist, or it is not recognized as a directory in the file system.

### Example


```python
import os
print(os.path.isdir('D:\\os_library\\Bilal_Iqbal.accdb'))
```

### Output

    False
    

This example checks if the path `D:\os_library\Bilal_Iqbal.accdb` is a directory. The output is `False` because `Bilal_Iqbal.accdb` is not a directory; it is a file (likely a Microsoft Access database file).

### Example


```python
import os
print(os.path.isdir('D:\\os_library\\UmerSaeed.csv'))
```
### Output

    False
    

This example checks if `D:\os_library\UmerSaeed.csv` is a directory. The output is `False` because `UmerSaeed.csv` is a file (likely a CSV file), not a directory.

## c). `os.path.isfile(path)`

The `os.path.isfile()` function in Python is used to check whether a given path refers to an **existing regular file** (not a directory, symbolic link, or other type of entry). It returns `True` if the path is a file and exists; otherwise, it returns `False`.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/isfile.png?raw=true)

## Checking if a Path is a File Using `os.path.isfile()`

The objective of the code is to check and print whether the specified paths are files.

### Example


```python
import os
print(os.path.isfile('D:\\os_library\\Bilal_Iqbal.accdb'))
```
### Output

    True
    

This example checks if the path `D:\os_library\Bilal_Iqbal.accdb` is an existing file. Since the output is `True`, it confirms that `Bilal_Iqbal.accdb` is present in the directory `D:\os_library` and is indeed a file.

### Example


```python
import os
print(os.path.isfile('D:\\os_library\\UmerSaeed.csv'))
```
### Output

    False
    

This example checks if the path `D:\os_library\UmerSaeed.csv` is an existing file. The output is `False`, indicating that the file `UmerSaeed.csv` does not exist in the specified directory.

### Example


```python
import os
print(os.path.isfile('D:\\os_library'))
```
### Output

    False
    

This example checks if the path `D:\os_library` is a file. The output is `False` because `D:\os_library` is a directory, not a file. The `os.path.isfile()` function will only return `True` for paths that are files.

### Example


```python
import os
print(os.path.isfile('D:\\os_library1'))
```
### Output

    False
    

This example checks if the path `D:\os_library1` is a file. The output is `False` because `D:\os_library1` does not exist at all in the file system. Since it doesn't exist, it cannot be a file.

## d) `os.access(path, mode)`

- Checks the **access permissions** of a given path for the current process.

Takes an additional argument mode to specify the type of access check:

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_access.png?raw=true)



### 1. os.F_OK

Check if the path exists (similar to `os.path.exists()`).

### 2. os.R_OK
Check if the path is readable.

### 3. os.W_OK
Check if the path is writable. 

### 4. os.X_OK
Check if the path is executable.

- Returns `True` if the specified access is allowed, `False` otherwise.

- `os.access()` is often used to check file accessibility rather than just existence.

## Checking File or Directory Access Permissions 

The objective of the code is to check and print the accessibility and permissions of a specified file or directory (`D:\\OS_Library\\Bilal_Iqbal.accdb`). It verifies whether the path exists, and checks if it is readable, writable, and executable.



```python
import os

path_to_check = 'D:\\OS_Library\\Bilal_Iqbal.accdb'

# Check if the path exists and is accessible
if os.access(path_to_check, os.F_OK):
    print(f"The file or directory '{path_to_check}' exists.")
else:
    print(f"The file or directory '{path_to_check}' does not exist.")

# Check if the path is readable
if os.access(path_to_check, os.R_OK):
    print(f"The file or directory '{path_to_check}' is readable.")
else:
    print(f"The file or directory '{path_to_check}' is not readable.")

# Check if the path is writable
if os.access(path_to_check, os.W_OK):
    print(f"The file or directory '{path_to_check}' is writable.")
else:
    print(f"The file or directory '{path_to_check}' is not writable.")

# Check if the path is executable
if os.access(path_to_check, os.X_OK):
    print(f"The file or directory '{path_to_check}' is executable.")
else:
    print(f"The file or directory '{path_to_check}' is not executable.")    

```
### Output

    The file or directory 'D:\OS_Library\Bilal_Iqbal.accdb' exists.
    The file or directory 'D:\OS_Library\Bilal_Iqbal.accdb' is readable.
    The file or directory 'D:\OS_Library\Bilal_Iqbal.accdb' is writable.
    The file or directory 'D:\OS_Library\Bilal_Iqbal.accdb' is executable.
    

## 5. Traversing Directories

Traversing directories involves systematically exploring and accessing directories and their subdirectories to locate files or gather information about the directory structure. This process is essential for tasks such as searching for specific files, performing batch operations across multiple directories, and generating comprehensive directory reports. By traversing directories, you can navigate through hierarchical file systems efficiently, enabling automation of tasks like backup, synchronization, and data analysis. Effective directory traversal ensures that you can handle complex directory structures and manage large sets of files with ease.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/traversing_walk.png?raw=true)

Key `os` Functions are;

- `os.walk()`

## a). `os.walk()`

The `os.walk()` function in Python is a powerful utility for navigating through directories and subdirectories in a file system. It generates the file names in a directory tree, rooted at a specified directory, and allows you to iterate over all the directories and files within that tree.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_walk.png?raw=true)

## Example-1


```python
import os

# Directory to start from
root_dir = 'D://OS_Library'

# Traverse the directory tree
for dirpath, dirnames, filenames in os.walk(root_dir):
    print(f"Current Directory: {dirpath}")
    print("Subdirectories:")
    for dirname in dirnames:
        print(f" - {dirname}")
    print("Files:")
    for filename in filenames:
        print(f" - {filename}")
    print()  # Newline for better readability
```

### Output

    Current Directory: D://OS_Library
    Subdirectories:
     - AhmedSaeed
     - AliSaeed
     - Ijlal_Khan
     - UmerSaeed
    Files:
     - Bilal_Iqbal.accdb
     - New Text Document.txt
     - New_version.xlsx
    
    Current Directory: D://OS_Library\AhmedSaeed
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\AliSaeed
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\Ijlal_Khan
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\UmerSaeed
    Subdirectories:
    Files:
    
    

## Top-Down Directory Traversal with `os.walk()`

## Example-2

This example demonstrates how to use `os.walk()` with the `topdown=True` parameter to traverse a directory tree from the top directory down to its subdirectories and files.


```python
import os

# Directory to start from
root_dir = 'D://OS_Library'

# Traverse the directory tree
for dirpath, dirnames, filenames in os.walk(root_dir,topdown=True):
    print(f"Current Directory: {dirpath}")
    print("Subdirectories:")
    for dirname in dirnames:
        print(f" - {dirname}")
    print("Files:")
    for filename in filenames:
        print(f" - {filename}")
    print()  # Newline for better readability
```
### Output

    Current Directory: D://OS_Library
    Subdirectories:
     - AhmedSaeed
     - AliSaeed
     - Ijlal_Khan
     - UmerSaeed
    Files:
     - Bilal_Iqbal.accdb
     - New Text Document.txt
     - New_version.xlsx
    
    Current Directory: D://OS_Library\AhmedSaeed
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\AliSaeed
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\Ijlal_Khan
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\UmerSaeed
    Subdirectories:
    Files:
    
    

Examples 1 and 2 perform the same operation because, by default, `os.walk()` traverses the directory tree from top to bottom. In Example-2, `topdown=True` is explicitly specified, but this is unnecessary since `topdown=True` is the default behavior of `os.walk()`. Both examples will output the current directory, subdirectories, and files in each directory from the root to the leaf nodes.

## Bottom-Up Directory Traversal with `os.walk()`

## Example-3

This example illustrates the use of `os.walk()` with the `topdown=False` parameter to traverse a directory tree from the bottom subdirectories up to the top directory.


```python
import os

# Directory to start from
root_dir = 'D://OS_Library'

# Traverse the directory tree
for dirpath, dirnames, filenames in os.walk(root_dir,topdown=False):
    print(f"Current Directory: {dirpath}")
    print("Subdirectories:")
    for dirname in dirnames:
        print(f" - {dirname}")
    print("Files:")
    for filename in filenames:
        print(f" - {filename}")
    print()  # Newline for better readability
```
### Output

    Current Directory: D://OS_Library\AhmedSaeed
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\AliSaeed
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\Ijlal_Khan
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library\UmerSaeed
    Subdirectories:
    Files:
    
    Current Directory: D://OS_Library
    Subdirectories:
     - AhmedSaeed
     - AliSaeed
     - Ijlal_Khan
     - UmerSaeed
    Files:
     - Bilal_Iqbal.accdb
     - New Text Document.txt
     - New_version.xlsx
    
    

## 6. Path Construction and Manipulation

Path construction and manipulation involve creating and modifying file and directory paths to manage files and directories effectively. This includes joining paths, splitting them into components, extracting file extensions, and determining base names and directories. Proper path handling is crucial for ensuring that your code can correctly locate and access files, regardless of the operating system or file system structure. By mastering path construction and manipulation, you can build flexible and portable code that adapts to different environments and directory layouts, making file operations more robust and reliable.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/path_construction.png?raw=true)

Key `os` Functions are;

- `os.path.join()`
- `os.path.split()`
- `os.path.splitext()`
- `os.path.basename()`
- `os.path.dirname()`
- `os.path.expanduser()`

The `os.path` functions (`os.path.join()`, `os.path.split()`, `os.path.splitext()`, `os.path.basename()`, `os.path.dirname()`, `os.path.expanduser()`) work even when a file or directory does not exist is because they are purely **string manipulation functions**.

The reason these `os.path` functions work without a valid file or directory is because they are simply processing the path as a string. They do not interact with the actual file system or validate the existence of the path, making them fast and useful for preparing paths for further file system operations.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/path_con_1.png?raw=true)

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/path_con_2.png?raw=true)

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/path_con_3.png?raw=true)

## a). `os.path.join()`

The `os.path.join()` function in Python is used to construct file and directory paths in a way that is compatible with the operating system’s path conventions. It ensures that the paths are correctly joined with the appropriate separators, making your code more portable across different operating systems (e.g., Windows, macOS, Linux).

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_join.png?raw=true)

## Listing All Directories and Files in a Directory Tree Using `os.walk()` and `os.path.join()`

The objective of this code is to traverse a specified directory tree and list all directories and files within it. Using `os.walk()`, the code iterates through each directory and subdirectory starting from the given root directory. For each directory and file encountered, it constructs their full paths using `os.path.join()` and prints them. This approach provides a comprehensive view of the directory structure and file organization, facilitating tasks such as directory auditing, file management, and system analysis.


```python
import os

# Ensure the provided path is absolute
dir = 'D://OS_Library'

# Walk the directory tree
for root, dirs, files in os.walk(dir):
    # List directories
    for dir_name in dirs:
        dir_path = os.path.join(root, dir_name)
        print(f"Directory: {dir_path}")
    
    # List files
    for file_name in files:
        file_path = os.path.join(root, file_name)
        print(f"File: {file_path}")
```
### Output

    Directory: D://OS_Library\AhmedSaeed
    Directory: D://OS_Library\AliSaeed
    Directory: D://OS_Library\Ijlal_Khan
    Directory: D://OS_Library\UmerSaeed
    File: D://OS_Library\Bilal_Iqbal.accdb
    File: D://OS_Library\New Text Document.txt
    File: D://OS_Library\New_version.xlsx
    

## b). `os.path.split()`

The `os.path.split` function separates a path into its head and tail components:

### Head 
The directory path, which is everything except the last component.

### Tail
The last component of the path, which is typically the filename or the last directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_split.png?raw=true)

### Example


```python
import os
os.path.split('')
```

### Output


    ('', '')



### Example


```python
import os
os.path.split('C:/Users/Pakistan/Downloads/File_Management/Chapter-03')
```

### Output

    ('C:/Users/Pakistan/Downloads/File_Management', 'Chapter-03')



### Example


```python
import os
os.path.split('C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering.png')
```

### Output


    ('C:/Users/Pakistan/Downloads/File_Management/Chapter-03',
     'Tools_and_Libraries_for_File_Filtering.png')



### Example


```python
import os
path = "C:/Users/Pakistan/Downloads/File_Management/Chapter-03"
head, tail = os.path.split(path)
print(head)  
print(tail) 
```
### Output
    C:/Users/Pakistan/Downloads/File_Management
    Chapter-03
    

### Example


```python
import os
path = "C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering.png"
head, tail = os.path.split(path)
print(head)  
print(tail) 
```
### Output

    C:/Users/Pakistan/Downloads/File_Management/Chapter-03
    Tools_and_Libraries_for_File_Filtering.png
    

## c). `os.path.splitext()`

The `os.path.splitext` function in Python is used to split a path into its root and extension components. This is particularly useful when you want to separate the filename from its extension, or when you need to handle files based on their extensions.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_splitext.png?raw=true)

### Example


```python
import os
os.path.splitext("C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering.png")
```


### Output

    ('C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering',
     '.png')



### Example


```python
import os
file_path = "C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering.png"
root, ext = os.path.splitext(file_path)
print(root)  
print(ext)
```
### Output

    C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering
    .png
    

### Example


```python
import os
file_path = "C:/Users/Pakistan1/Tools_and_Libraries_for_File_Filtering.png"
root, ext = os.path.splitext(file_path)
print(root)  
print(ext)
```
### Output

    C:/Users/Pakistan1/Tools_and_Libraries_for_File_Filtering
    .png
    

## d). `os.path.basename()`

The `os.path.basename` function in Python is used to extract the base name of a file or directory from a given path. The base name is the final component of the path, which could be a filename or the name of the last directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_basename.png?raw=true)

### Example


```python
import os
file_path = "D:/os_library/Bilal_Iqbal.accdb"
basename = os.path.basename(file_path)
print(basename)
```

### Output

    Bilal_Iqbal.accdb
    

### Example


```python
import os
file_path = "D:/os_library/UmerSaeed.csv"
basename = os.path.basename(file_path)
print(basename)
```
### Output

    UmerSaeed.csv
    

### Example


```python
import os
file_path = "C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering.png"
basename = os.path.basename(file_path)
print(basename) 
```
### Output

    Tools_and_Libraries_for_File_Filtering.png
    

## e). `os.path.dirname()`

The `os.path.dirname` function in Python is used to extract the directory path from a given file path. Essentially, it returns everything in the path except for the last component, which could be a file name or the name of the last directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_dirname.png?raw=true)

### Example


```python
import os
file_path = "D:/os_library/Bilal_Iqbal.accdb"
dirname = os.path.dirname(file_path)
print(dirname)  
```
### Output

    D:/os_library
    

### Example


```python
import os
file_path = "C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering.png"
dirname = os.path.dirname(file_path)
print(dirname) 
```

### Output

    C:/Users/Pakistan/Downloads/File_Management/Chapter-03
    

### Example


```python
import os
file_path = "C:/Users/Pakistan/Downloads/File_Management/Chapter-03/Tools_and_Libraries_for_File_Filtering.png"
dirname = os.path.dirname(file_path)
print(dirname) 
```
### Output

    C:/Users/Pakistan/Downloads/File_Management/Chapter-03
    

### Example


```python
import os
file_path = "D:/os_library"
dirname = os.path.dirname(file_path)
print(dirname) 
```

### Output

    D:/
    

## f). `os.path.expanduser()`

The `os.path.expanduser` function in Python is used to expand the `~ `(tilde) symbol to the full path of the user's home directory. This is particularly useful when writing cross-platform code where you want to refer to a user's home directory without hardcoding the path.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_expanduser.png?raw=true)

### Example


```python
import os
os.path.expanduser('~')
```


### Output

    'C:\\Users\\Pakistan'



## Expanding the Home Directory Path Using os.path.expanduser


```python
import os
os.path.expanduser('~/Daily_Audits_26052024')
```

### Output

    'C:\\Users\\Pakistan/Daily_Audits_26052024'



## Expanding and Validating a User Directory Path with `os.path.expanduser` and `os.path.exists`


```python
import os

expanded_path = os.path.expanduser('~/Daily_Audits_26052024')
print(f"Expanded Path: {expanded_path}")

# Check if the path exists
if os.path.exists(expanded_path):
    print("The path exists.")
else:
    print("The path does not exist.")
```
### Output

    Expanded Path: C:\Users\Pakistan/Daily_Audits_26052024
    The path exists.
    

## 7. Retrieving File Information

Retrieving file information involves accessing metadata about files, such as their size, creation and modification dates, and various attributes. This information is essential for tasks such as monitoring file changes, managing storage, and performing data analysis. By obtaining detailed file information, you can make informed decisions about file handling, optimize performance, and ensure that your applications handle files appropriately based on their properties. This capability is crucial for both system administration and application development, enabling efficient and effective file management.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/file_information.png?raw=true)

Key `os` Functions are;

- `os.stat()`
- `os.path.getsize()`

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/file_size_info.png?raw=true)

## a). `os.stat()`

The `os.stat()` function in Python provides detailed information about a file or directory. It returns a `os.stat_result` object that contains various attributes related to the file or directory, such as its size, permissions, and modification times.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_stats.png?raw=true)

### Purpose
Retrieves information about a specified file or directory.

### Usage 
Provides a `os.stat_result` object with multiple attributes that describe the file or directory.

### Syntax:`os.stat(path)`

   - `path:` The path to the file or directory you want to get information about.

### Attributes of os.stat_result
The `os.stat_result` object has several attributes, including:

### 1. st_mode
File mode (permissions and type).

### 2. st_ino
Inode number.

### 3. st_dev
Device ID.

### 4. st_nlink 
Number of hard links.

### 5. st_uid
User ID of the file owner.

### 6. st_gid
Group ID of the file owner.

### 7. st_size
Size of the file in bytes.

### 8. st_atime 
Last access time (in seconds since the epoch).

### 9. st_mtime
Last modification time (in seconds since the epoch).

### 10. st_ctime 
Creation time (in seconds since the epoch) or metadata change time, depending on the platform.

## Basic File Information

The objective of the code is to retrieve and display detailed information about a file named `Bilal_Iqbal.accdb` using Python's `os.stat` function.


```python
import os
import time

# Specify the path to the file
file_path = 'D:/os_library/Bilal_Iqbal.accdb'

# Get file statistics
stat_info = os.stat(file_path)

# Print file information
print(f"Directory size: {stat_info.st_size / (1024 ** 3):.2f} GB")
print(f"Last modified: {time.ctime(stat_info.st_mtime)}")
print(f"Last accessed: {time.ctime(stat_info.st_atime)}")
print(f"File permissions: {oct(stat_info.st_mode)}")
print(f"Inode number: {stat_info.st_ino}")
print(f"Device ID: {stat_info.st_dev}")
print(f"Number of hard links: {stat_info.st_nlink}")
print(f"User ID of the file owner: {stat_info.st_uid}")
print(f"Group ID of the file owner: {stat_info.st_gid}")
```
### Output

    Directory size: 0.00 GB
    Last modified: Thu Sep  5 14:49:34 2024
    Last accessed: Tue Sep 10 20:37:17 2024
    File permissions: 0o100666
    Inode number: 36028797018973191
    Device ID: 1347891562
    Number of hard links: 1
    User ID of the file owner: 0
    Group ID of the file owner: 0
    

## Directory Information

The objective of the code is to retrieve and display detailed information about a directory named `D://os_library` using Python's `os.stat` function.


```python
import os
import time

# Specify the path to the directory
directory_path = 'D://os_library'

# Get directory statistics
stat_info = os.stat(directory_path)

# Print directory information
print(f"Directory size: {stat_info.st_size / (1024 ** 3):.2f} GB")
print(f"Last modified: {time.ctime(stat_info.st_mtime)}")
print(f"Last accessed: {time.ctime(stat_info.st_atime)}")
print(f"File permissions: {oct(stat_info.st_mode)}")
print(f"Inode number: {stat_info.st_ino}")
print(f"Device ID: {stat_info.st_dev}")
print(f"Number of hard links: {stat_info.st_nlink}")
print(f"User ID of the file owner: {stat_info.st_uid}")
print(f"Group ID of the file owner: {stat_info.st_gid}")
```
### Output
    Directory size: 0.00 GB
    Last modified: Tue Sep 10 20:37:17 2024
    Last accessed: Tue Sep 10 20:39:36 2024
    File permissions: 0o40777
    Inode number: 42221246506606085
    Device ID: 1347891562
    Number of hard links: 1
    User ID of the file owner: 0
    Group ID of the file owner: 0
    

## b). `os.path.getsize()`

The `os.path.getsize` function in Python is used to obtain the size of a file or directory. It returns the size of the file in bytes. If you provide a directory path, it will raise a `TypeError` because `os.path.getsize` does not support directories.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_path_size.png?raw=true)

### Example

The objective of the code is to find and display the size of the file `Bilal_Iqbal.accdb` located in the `D:/os_library` directory. It uses the `os.path.getsize()` function to get the file size in bytes and then prints the file size along with its path.


```python
import os
file_path = "D:/os_library/Bilal_Iqbal.accdb"
size = os.path.getsize(file_path)
print(f"Size of {file_path}: {size} bytes")
```
### Output

    Size of D:/os_library/Bilal_Iqbal.accdb: 495616 bytes
    

### Example

The objective of the code is to find and display the size of the directory entry `D:/os_library` in bytes. However, this size is not the total size of all files and subdirectories within `D:/os_library`; it only shows the size of the directory entry itself.


```python
import os
file_path = "D:/os_library"
size = os.path.getsize(file_path)
print(f"Size of {file_path}: {size} bytes")
```
### Output

    Size of D:/os_library: 4096 bytes
    

## 8. Creating Directories

Creating directories is a fundamental operation for organizing files and structuring data on a file system. It involves generating new folders to group related files, manage data hierarchies, and maintain a clean and organized storage environment. This operation is essential for setting up project structures, organizing data for applications, and ensuring that files are stored in appropriate locations. By effectively creating directories, you can streamline file management, enhance accessibility, and support the logical organization of information.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/cr_dir.png?raw=true)

Key `os` Functions are;

- `os.mkdir()`
- `os.makedirs()`

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/creating_directories.png?raw=true)

## a). `os.mkdir()`

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_mkdir.png?raw=true)

### Purpose 
Creates a single directory at the specified path.

### Usage 
It can create only one directory at a time and will raise an `OSError` if the directory already exists or if the parent directory does not exist.

## Syntax: `os.mkdir(path, mode=0o777)`
  - **`path`**: The path to the directory you want to create.
  - **`mode`:** Optional. The permissions for the directory, represented as an octal number (default is `0o777`).

## Creating a Directory with Error Handling

The objective of the code is to create a new directory with a specified name (`new_directory`) using Python's `os` module. The code checks for potential errors: if the directory already exists (`FileExistsError`), if there is no permission to create the directory (`PermissionError`), or any other unexpected error. If the directory is created successfully, it prints a confirmation message; otherwise, it provides an appropriate error message.


```python
import os

# Specify the directory path
directory_path = 'D:/os_library/new_directory'

# Create a single directory
try:
    os.mkdir(directory_path)
    print(f"Directory '{directory_path}' created successfully.")
except FileExistsError:
    print(f"Directory '{directory_path}' already exists.")
except PermissionError:
    print(f"Permission denied to create directory '{directory_path}'.")
except Exception as e:
    print(f"An error occurred: {e}")
```

### Output

    Directory 'D:/os_library/new_directory' created successfully.
    

`os.listdir()` is used to list the files and directories in the current working directory. If `new_directory` appears in the list, it confirms that the directory was created successfully.


```python
os.listdir()
```




    ['AhmedSaeed',
     'AliSaeed',
     'Bilal_Iqbal.accdb',
     'Ijlal_Khan',
     'New Text Document.txt',
     'new_directory',
     'New_version.xlsx',
     'UmerSaeed']



## b). `os.makedirs()`

### Purpose 
Creates a directory tree, i.e., it can create intermediate directories if they do not exist.

### Usage
It can create multiple directories at once, including all necessary parent directories.

### Syntax: `os.makedirs(name, mode=0o777, exist_ok=False)`

  - **`name`**: The path of the directory to create, including any intermediate directories.
    
  - **`mode`**: Optional. The permissions for the directories, represented as an octal number (default is `0o777`).
    
   - **`exist_ok`**: Optional. If `True`, it will not raise an error if the target directory already exists (default is `False`). 

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_makedirs.png?raw=true)

## Creating a Directory Tree with Intermediate Directories 

The objective of the code is to create a directory tree with multiple nested directories (`parent_dir/child_dir/grandchild_dir`). It uses the `os.makedirs` function to create all the necessary directories, including any intermediate ones that do not exist. If the directory tree is created successfully, it prints a confirmation message; otherwise, it handles and displays any errors that occur, such as permission issues.


```python
import os

# Specify the directory path with intermediate directories
directory_path = 'D:/os_library/parent_dir/child_dir/grandchild_dir'

# Create a directory tree
try:
    os.makedirs(directory_path, exist_ok=True)
    print(f"Directory tree '{directory_path}' created successfully.")
except PermissionError:
    print(f"Permission denied to create directory tree '{directory_path}'.")
except Exception as e:
    print(f"An error occurred: {e}")
```

### Output

    Directory tree 'D:/os_library/parent_dir/child_dir/grandchild_dir' created successfully.
    

To confirm that the directory tree has been created correctly, we can use the `os.listdir()` function to display the contents of the specified directory.


```python
os.listdir('D:/os_library')
```




    ['AhmedSaeed',
     'AliSaeed',
     'Bilal_Iqbal.accdb',
     'Ijlal_Khan',
     'New Text Document.txt',
     'new_directory',
     'New_version.xlsx',
     'parent_dir',
     'UmerSaeed']



## 9. Deleting Directories

Deleting directories is an essential task for managing file systems, allowing you to remove unwanted or obsolete folders and their contents. This operation helps in freeing up storage space, maintaining an organized file structure, and cleaning up after file operations or completed projects. When deleting directories, it’s important to ensure that they are no longer needed and that their removal will not impact other files or processes. Proper handling of directory deletion can help prevent accidental loss of important data and maintain an efficient and clutter-free file system.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/del_dir.png?raw=true)

Key `os` Functions are;

- `os.rmdir()`
- `os.removedirs()`

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/deleting_directories.png?raw=true)

## a). `os.rmdir()`

### Purpose
Removes a single empty directory.

### Usage
This function can only remove directories that are empty. It will raise an `OSError` if the directory is not empty or if it does not exist.

### Syntax: `os.rmdir(path)`

  - **`path`**: The path to the directory you want to remove.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_rmdir.png?raw=true)

## Removing an Empty Directory with Error Handling

The objective of the code is to remove an empty directory (`new_directory`) using Python's `os.rmdir` function. The code attempts to delete the specified directory and, if successful, prints a confirmation message. If the directory does not exist (`FileNotFoundError`) or if there is an error (such as the directory not being empty), it catches the error and displays an appropriate message.


```python
import os

# Specify the directory path to remove
directory_path = 'new_directory'

# Remove the empty directory
try:
    os.rmdir(directory_path)
    print(f"Directory '{directory_path}' removed successfully.")
except FileNotFoundError:
    print(f"Directory '{directory_path}' does not exist.")
except OSError as e:
    print(f"Error removing directory '{directory_path}': {e}")
```

### Output

    Directory 'new_directory' removed successfully.
    

`os.listdir()` is used to list the files and directories in the current working directory. If `new_directory` does not appear in the list, it confirms that the directory has been deleted successfully.


```python
os.listdir()
```




    ['AhmedSaeed',
     'AliSaeed',
     'Bilal_Iqbal.accdb',
     'Ijlal_Khan',
     'New Text Document.txt',
     'New_version.xlsx',
     'parent_dir',
     'UmerSaeed']



## b). `os.removedirs()`

### Purpose 
Removes a directory tree, meaning it will remove the specified directory and any empty parent directories.

### Usage 
This function removes the target directory and its empty parent directories recursively. It will raise an `OSError` if any directory in the path is not empty.

### Syntax: `os.removedirs(name)`
   - **`name:`** The path to the directory you want to remove, including any empty parent directories.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_removedirs.png?raw=true)

## Removing a Nested Directory Structure

The objective of the code is to remove a nested directory structure (`D:\os_library\parent_dir\child_dir\grandchild_dir`). It uses the `os.removedirs` function to delete the directories, including any empty intermediate ones. If the directory structure is removed successfully, it prints a confirmation message. If the directory does not exist or if an error occurs during the removal, it handles and displays an appropriate error message.


```python
import os

# Create a nested directory structure for demonstration
nested_directory_path = 'D:\os_library\parent_dir\child_dir\grandchild_dir'


# Remove the nested directory structure
try:
    os.removedirs(nested_directory_path)
    print(f"Directory tree '{nested_directory_path}' removed successfully.")
except FileNotFoundError:
    print(f"Directory tree '{nested_directory_path}' does not exist.")
except OSError as e:
    print(f"Error removing directory tree '{nested_directory_path}': {e}")
```

### Output

    Directory tree 'D:\os_library\parent_dir\child_dir\grandchild_dir' removed successfully.
    

`os.listdir()` is used to list the files and directories in the current working directory. If `parent_dir` does not appear in the list, it confirms that the directory has been deleted successfully.


```python
os.listdir()
```




    ['AhmedSaeed',
     'AliSaeed',
     'Bilal_Iqbal.accdb',
     'Ijlal_Khan',
     'New Text Document.txt',
     'New_version.xlsx',
     'UmerSaeed']



## 10. Renaming and Moving Files

Renaming and moving files are key operations for managing and organizing data within a file system. Renaming allows you to change a file's name to make it more descriptive or consistent with a naming convention. Moving files, on the other hand, involves relocating them from one directory to another, which is useful for reorganization, archiving, or distributing files across different locations. These operations help maintain a structured file system, improve accessibility, and ensure that files are logically grouped and easy to find. Proper handling of file renaming and moving is essential for effective data management and efficient workflow.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/file_manag_cycle.png?raw=true)

Key `os` Functions are;

- `os.rename()`
- `os.replace()`

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/renaming_and_moving_files.png?raw=true)

## a). `os.rename()`

### Purpose 
Renames or moves a file or directory.

### Usage
You provide the current path and the new path (which can include a new name and/or location). If the new path is in a different directory, the file or directory will be moved to that new location.

### Syntax: `os.rename(src, dst)`
  - `src`: The current path of the file or directory you want to rename or move.
  - `dst`: The new path (including the new name) of the file or directory.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_rename.png?raw=true)

## Renaming a File with Error Handling

The objective of the code is to rename a file from `New Text Document.txt` to `Kashif_Hameed.txt` using Python's `os.rename` function. The code attempts to change the file name and, if successful, prints a confirmation message. If the original file does not exist (`FileNotFoundError`), if there is no permission to rename the file (`PermissionError`), or if any other error occurs, it catches the error and displays an appropriate message.


```python
import os

# Specify the original and new file paths
original_file = 'New Text Document.txt'
new_file = 'Kashif_Hameed.txt'

# Rename the file
try:
    os.rename(original_file, new_file)
    print(f"File renamed from '{original_file}' to '{new_file}'.")
except FileNotFoundError:
    print(f"File '{original_file}' does not exist.")
except PermissionError:
    print(f"Permission denied to rename '{original_file}'.")
except Exception as e:
    print(f"Error renaming file: {e}")
```

### Output

    File renamed from 'New Text Document.txt' to 'Kashif_Hameed.txt'.
    

To verify the renaming operation, use `os.listdir()` to list the files in the current directory and confirm that `'New Text Document.txt'` has been renamed  by `'Kashif_Hameed.txt'`.


```python
os.listdir()
```




    ['AhmedSaeed',
     'AliSaeed',
     'Bilal_Iqbal.accdb',
     'Ijlal_Khan',
     'Kashif_Hameed.txt',
     'New_version.xlsx',
     'UmerSaeed']



## Renaming a Directorywith Error Handling in Python

The objective of the code is to rename a directory from `AhmedSaeed` to `AhmadSaeed` using Python's `os.rename` function. The code attempts to rename the specified directory and, if successful, prints a confirmation message. If the original directory does not exist (`FileNotFoundError`), if there is no permission to rename the directory (`PermissionError`), or if any other error occurs, it catches the error and displays an appropriate message.


```python
import os

# Specify the original and new folder paths
original_file = 'AhmedSaeed'
new_file = 'AhmadSaeed'

# Rename the file
try:
    os.rename(original_file, new_file)
    print(f"File renamed from '{original_file}' to '{new_file}'.")
except FileNotFoundError:
    print(f"File '{original_file}' does not exist.")
except PermissionError:
    print(f"Permission denied to rename '{original_file}'.")
except Exception as e:
    print(f"Error renaming file: {e}")
```

### Output

    File renamed from 'AhmedSaeed' to 'AhmadSaeed'.
    

To verify the renaming operation, use `os.listdir()` to list the files and directories in the current directory and confirm that the subdirectory `'AhmedSaeed'` has been renamed to `'AhmadSaeed'`.


```python
os.listdir()
```




    ['AhmadSaeed',
     'AliSaeed',
     'Bilal_Iqbal.accdb',
     'Ijlal_Khan',
     'Kashif_Hameed.txt',
     'New_version.xlsx',
     'UmerSaeed']



## Moving a File to a Different Directory

The objective of the code is to move a file named `Kashif_Hameed.txt` to a new directory named `UmerSaeed` using Python's `os.rename` function. The code first checks if the target directory exists, and if not, it creates the directory using `os.makedirs`. It then attempts to move the file to the new location. If the file is moved successfully, it prints a confirmation message. If the file does not exist (`FileNotFoundError`), if there is no permission to move the file (`PermissionError`), or if any other error occurs, it catches the error and displays an appropriate message.


```python
os.listdir('D:/os_library/UmerSaeed')
```




    []



The output of os.listdir(`'D:/os_library/UmerSaeed'`) is an empty list, which means there are currently no files in this directory.


```python
import os

# Specify the current file path and the new path
file_to_move = 'Kashif_Hameed.txt'
new_directory = 'UmerSaeed'
new_location = os.path.join(new_directory, file_to_move)

# Create the new directory if it doesn't exist
os.makedirs(new_directory, exist_ok=True)

# Move the file
try:
    os.rename(file_to_move, new_location)
    print(f"File moved to '{new_location}'.")
except FileNotFoundError:
    print(f"File '{file_to_move}' does not exist.")
except PermissionError:
    print(f"Permission denied to move '{file_to_move}'.")
except Exception as e:
    print(f"Error moving file: {e}")
```

### Output

    File moved to 'UmerSaeed\Kashif_Hameed.txt'.
    

The output of os.listdir(`'D:/os_library/UmerSaeed'`) shows that `'Kashif_Hameed.txt'` has been moved to the specified directory successfully.


```python
os.listdir('D:/os_library/UmerSaeed')
```




    ['Kashif_Hameed.txt']



## b). `os.replace()`

The `os.replace()` function in Python is used to replace a file or directory at a given path with a new file or directory. If the destination file already exists, it will be replaced by the source file. This function is particularly useful when you need to replace files while ensuring that no data is lost or corrupted during the replacement process.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/os_library/os_replace.png?raw=true)

## Replacing a File

Suppose you have a file `New_version.xlsx` and you want to replace it with `Old_version.xlsx`. You can use `os.replace()` to perform this operation.


```python
import os

# Paths to the source and destination files
src = 'D:/os_library/New_version.xlsx'
dst = 'D:/os_library/old_version.xlsx'

# Replace the old version with the new version
os.replace(src, dst)

print("File replaced successfully.")
```

### Output

    File replaced successfully.
    

After executing `os.replace(src, dst)`, use `os.listdir()` to list the files and directories. The output confirms that `'New_version.xlsx'` has been replaced with `'old_version.xlsx'` successfully.


```python
os.listdir()
```




    ['AhmadSaeed',
     'AliSaeed',
     'Bilal_Iqbal.accdb',
     'Ijlal_Khan',
     'old_version.xlsx',
     'UmerSaeed']



## Replacing a Directory

Similarly, you can use `os.replace()` to replace a directory.


```python
import os

# Paths to the source and destination files
src = 'D:/os_library/AhmadSaeed'
dst = 'D:/os_library/AhmedSaeed'

# Replace the old data directory with the new data directory
os.replace(src, dst)

print("Directory replaced successfully.")
```
### Output

    Directory replaced successfully.
    

After executing `os.replace(src, dst)`, use `os.listdir()` to list the files and directories. The output confirms that the directory name 'AhmadSaeed' has been replaced with 'AhmedSaeed' successfully.


```python
os.listdir()
```




    ['AhmedSaeed',
     'AliSaeed',
     'Bilal_Iqbal.accdb',
     'Ijlal_Khan',
     'old_version.xlsx',
     'UmerSaeed']



![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/banoqabil.png?raw=true)
