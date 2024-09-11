# Disk Management Using `shutil`

Disk management is a critical aspect of maintaining a healthy computing environment. It involves monitoring, managing, and optimizing the storage capacity of drives to ensure they operate efficiently. In Python, the `shutil` module provides tools to handle disk usage statistics, making it easier to monitor available space, detect potential issues, and automate disk space management tasks.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/managing_disk_space/efficient_disk_management_00.png?raw=true)

Understanding disk usage is vital for various applications, from personal computer maintenance to server management in production environments. Insufficient disk space can lead to application failures, performance degradation, and data loss. By using Python's `shutil` library, developers and system administrators can build scripts to automate disk management tasks, such as checking available space, cleaning up temporary files, and ensuring critical operations have sufficient space to execute.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/managing_disk_space/efficient_disk_management_01.png?raw=true)

## Understanding `shutil.disk_usage`

The `shutil` module, part of Python's standard library, offers a high-level interface for various file operations. One of its most useful functions for disk management is `shutil.disk_usage()`, which retrieves disk usage statistics for a specified path.

The shutil.disk_usage() function returns a named tuple with three values:

**1. Total:**: The total size of the filesystem in bytes.

**2. Used:** The total amount of space used by files in bytes.

**3. Free:** The total amount of free space available in bytes.

To use `shutil.disk_usage()`, you need to specify a directory path (e.g., `'/'` for the root directory on Unix-based systems or `'C:/'` for the main drive on Windows). The function then calculates the disk space statistics for that particular path.

The values returned by shutil.disk_usage() are in bytes, so to convert them to more human-readable units like gigabytes (GB), you divide by 1024<sup>3</sup>.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Management_Operations/Managing_Disk_Space.png?raw=true)

## 1. Basic Disk Usage Information

Show how to check the total, used, and free space on the main disk (root directory) of the system.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Management_Operations/Example-01.png?raw=true)


![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/managing_disk_space/Managing_Disk_Space.png?raw=true)

```python
# import required libraries
import shutil

# Get disk usage for the root directory
usage = shutil.disk_usage('/')

print(f"Total: {usage.total / (1024**3):.2f} GB")
print(f"Used: {usage.used / (1024**3):.2f} GB")
print(f"Free: {usage.free / (1024**3):.2f} GB")
```
### Output

    Total: 291.54 GB
    Used: 147.70 GB
    Free: 143.84 GB
    

## 2. Disk Usage for a Specific Directory

Demonstrate how to find out the total, used, and free space for a specific folder or directory on your computer.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Management_Operations/Example-02.png?raw=true)


```python
# import required libraries
import shutil

# Get disk usage for a specific directory
usage = shutil.disk_usage('D:/')

print(f"Total: {usage.total / (1024**3):.2f} GB")
print(f"Used: {usage.used / (1024**3):.2f} GB")
print(f"Free: {usage.free / (1024**3):.2f} GB")

```
### Output

    Total: 293.27 GB
    Used: 259.72 GB
    Free: 33.55 GB
    

## 3. Handling Exceptions

Show how to safely check disk usage for a directory, including handling cases where the directory might not exist or other errors occur.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Management_Operations/Example-03.png?raw=true)


```python
# import required libraries
import os
import shutil


path = 'D:/Copy/Umer_Saeed'

try:
    # Check if the path exists before getting disk usage
    if os.path.exists(path):
        usage = shutil.disk_usage(path)
        print(f"Total: {usage.total / (1024**3):.2f} GB")
        print(f"Used: {usage.used / (1024**3):.2f} GB")
        print(f"Free: {usage.free / (1024**3):.2f} GB")
    else:
        print(f"The path '{path}' does not exist.")
except Exception as e:
    print(f"An error occurred: {e}")
```
### Output

    Total: 293.27 GB
    Used: 259.72 GB
    Free: 33.55 GB
    

## 4. Disk Usage for Multiple Drives

Explain how to check the total, used, and free space for multiple drives (like `C:`, `D:`, etc.) and handle situations where a drive is not found or can't be accessed.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/File_Management_Operations/Example-04.png?raw=true)


```python
# import required libraries
import shutil

# List of drives or paths to check
paths = ['C:/', 'D:/', 'E:/', 'H:/']

for path in paths:
    try:
        usage = shutil.disk_usage(path)
        print(f"Drive {path}:")
        print(f"  Total: {usage.total / (1024**3):.2f} GB")
        print(f"  Used: {usage.used / (1024**3):.2f} GB")
        print(f"  Free: {usage.free / (1024**3):.2f} GB")
    except FileNotFoundError:
        print(f"Drive {path} not found.")
    except PermissionError:
        print(f"Permission denied to access {path}.")
```
### Output

    Drive C:/:
      Total: 291.54 GB
      Used: 147.70 GB
      Free: 143.84 GB
    Drive D:/:
      Total: 293.27 GB
      Used: 259.72 GB
      Free: 33.55 GB
    Drive E:/:
      Total: 367.33 GB
      Used: 329.75 GB
      Free: 37.58 GB
    Drive H:/ not found.
