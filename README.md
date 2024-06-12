#  [Umer Saeed](https://www.linkedin.com/in/engumersaeed/)
Sr. RF Planning & Optimization Engineer<br>
BSc Telecommunications Engineering, School of Engineering<br>
MS Data Science, School of Business and Economics<br>
**University of Management & Technology**<br>
**Mobile:**     +923018412180<br>
**Email:**  umersaeed81@hotmail.com<br>
**Address:** Dream Gardens,Defence Road, Lahore<br>




<h1 align="center">File Management Operations</h1>



In the realm of programming, file management is a fundamental skill that transcends experience levels. Proficient handling of file operations is crucial for a wide array of tasks, from simple file copying to complex data organization and workflow automation.

# Why File Management Is Essential?
File manipulation is a cornerstone of many programming tasks. Whether you are organizing data, automating processes, or optimizing workflows, understanding file operations is crucial. This chapter aims to empower readers with a comprehensive understanding of these operations, emphasizing both syntax and practical applications.

- **Data Organization:** Efficient file management helps in organizing and structuring data, making it accessible and manageable.

- **Process Automation:** Automating file operations saves time and reduces the potential for human error.

- **Workflow Optimization:** Streamlined file management processes contribute to more efficient and effective workflows.

- **Copy Files:** Duplicating files from one location to another, ensuring a backup or creating copies for different tasks. This operation is fundamental when you need to preserve the original file while working on a copy.

- **Move Files:** Relocating files to a new directory path, effectively changing their location within the filesystem. This is useful for organizing files into appropriate directories or transferring files to different storage locations.

- **Delete Files:** Removing files from the filesystem, which is essential for freeing up space and managing storage. Proper file deletion helps maintain an organized and clutter-free directory structure.

- **Create Directories:** Making new directories to organize files, allowing for a structured and hierarchical storage system. This is important for keeping related files together and simplifying file retrieval.

- **Delete Directories:** Removing directories and their contents, often necessary when directories are no longer needed. This operation helps in maintaining an efficient and tidy file system by eliminating unused or outdated directories.

- **Rename Files:** Changing the name of a file, which can be crucial for clarity, organization, or adhering to naming conventions. Renaming files helps in identifying and categorizing them appropriately.

- **List Directory Contents:** Viewing the contents of a directory, providing a snapshot of the files and subdirectories within. This operation is useful for gaining an overview of what is stored in a particular directory and for verifying file presence.

- **Zip Files:** Compressing files into a zip archive, which reduces their size for storage and transfer. Zipping files is essential for saving disk space and for efficient file sharing.

- **Unzip Files:** Extracting files from a zip archive, allowing access to compressed files. Unzipping is necessary to retrieve the original files for use after they have been compressed for storage or transfer.

These operations form the foundation of efficient and effective file handling, ensuring that you can manage files and directories proficiently in various programming scenarios.

# 1. File Copy Operations

Copying files is one of the most fundamental and frequently performed operations in file management. Whether you're duplicating files for backup purposes, distributing copies to different locations, or preparing files for further processing, understanding how to efficiently and effectively copy files is essential. This chapter delves into the various aspects of copy operations, providing practical insights and detailed examples to equip you with the necessary skills to handle file copying tasks in Python.

## 1.1 Simple File Copy

The most basic form of copying involves duplicating a single file from one location to another. This operation preserves the original file while creating an identical copy at the target location.

In this section, we will explore several examples that demonstrate different scenarios and techniques for copying files. Each example builds upon the previous one, introducing new checks and safeguards to handle common issues that can arise during file copying operations. These examples highlight the importance of verifying the existence of source files and destination directories, handling potential overwrites, and ensuring robust and error-free copy operations.

### [Basic File Copy](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Simple_File_Copy/Example-01.md)<br>

This example demonstrates how to copy a single file from a source location to a destination folder using the **shutil.copy()** function. This operation creates an exact copy of the file in the specified destination.

### [File Copy with Existence Check](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Simple_File_Copy/Example-02.md)

This example enhances the basic file copy by first checking if the source file exists before attempting to copy it. If the file is found, it is copied to the destination folder, and a success message is printed. If not, an error message is displayed.


### [File Copy with Destination Folder Check](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Simple_File_Copy/Example-03.md)

This example further improves the file copy operation by checking if the destination folder exists. If the destination folder is not found, an error message is displayed, preventing the copy operation from proceeding.

### [Comprehensive Error Handling](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Simple_File_Copy/Example-04.md)

This version combines checks for both the existence of the source file and the destination folder before performing the copy operation, providing more comprehensive error handling compared to previous examples.


### [Creating Destination Folder](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Simple_File_Copy/Example-05.md)

This code creates the destination folder if it does not already exist and checks if the source file exists. If the source file is found, it copies the file; otherwise, it displays an error message.

### [Avoiding Overwrites by Renaming](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Simple_File_Copy/Example-06.md)

This example ensures that the copied file does not overwrite an existing file in the destination folder by appending an incremental suffix to the filename if a file with the same name already exists. This guarantees that all copies are retained uniquely.

### [Selective Files Copy](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Simple_File_Copy/Example-07.md)

This example demonstrates how to selectively copy multiple files from a list of source files to a destination folder. The code checks if each file exists and copies it if it does. If the destination folder does not exist, it is created.

### [Selective Files Copy Avoiding Overwrites by Renaming](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Simple_File_Copy/Example-08.md)

This example extends the selective files copy by adding functionality to avoid overwriting existing files in the destination folder. If a file with the same name already exists, the code generates a new filename with an incremental suffix to ensure that each file is copied without overwriting any existing files.

## 1.2 Copying Multiple Files

Copying multiple files from one directory to another is a common requirement in many applications. This operation involves iterating over a set of files and duplicating each one at the target location. In this section, we will explore several examples that demonstrate different scenarios and techniques for copying multiple files. Each example builds upon the previous one, introducing new checks and safeguards to handle common issues that can arise during these operations. These examples highlight the importance of filtering out subfolders, handling potential overwrites, and ensuring robust and error-free copy operations.

### [Copying All Files from a Directory](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Multiple_Files/Example-09.md)
This example demonstrates how to copy all files from a source directory to a destination directory. It iterates over each file in the source directory and duplicates it in the destination directory.

### [Copying All Files and Renaming to Avoid Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Multiple_Files/Example-10.md)
This example improves upon the previous one by adding functionality to avoid overwriting existing files in the destination folder. It generates new filenames with an incremental suffix if a file with the same name already exists.

### [Copying Only Files from a Directory](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Multiple_Files/Example-11.md)

This example refines the copying process by filtering out subfolders and only copying files from the source directory to the destination directory. This ensures that only the intended files are copied without including any subfolder structures

### [Copying Only Files and Renaming to Avoid Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Multiple_Files/Example-12.md)

This example combines the functionality of filtering out subfolders and avoiding overwrites by renaming files. It ensures that only files are copied, and if a file with the same name already exists in the destination folder, it generates a new filename to prevent overwriting.

## 1.3 Conditional Copying

Conditional copying involves applying specific criteria to determine which files should be copied. This approach allows for more refined and controlled file copying operations based on file types, names, or other attributes. In this section, we explore examples where files are selectively copied based on their extensions and other conditions, ensuring that only the relevant files are transferred while handling potential overwrites and preserving metadata.

### 1.3.1 Copying Files Based on File Extensions

In this subsection, we focus on copying files based on their file extensions. This method is useful when you only need to copy files with specific extensions from a directory, thereby avoiding unnecessary data transfer and saving time.

### [Copying Only Excel Files](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_File_Extensions/Example-13.md)

This example demonstrates how to copy only .xlsx files from a source directory to a destination directory. It filters files based on their extensions and copies only the matching files.

### [Copying Excel Files and Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_File_Extensions/Example-14.md)

Building upon the previous example, this script adds functionality to avoid overwriting existing files in the destination folder. It generates new filenames with an incremental suffix if a file with the same name already exists.

### [Copying Excel and Text Files](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_File_Extensions/Example-15.md)

This example extends the filtering criteria to include both .xlsx and .txt files. It demonstrates how to copy multiple specific file types from a source directory to a destination directory.

### [Copying Excel and Text Files with Renaming to Avoid Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_File_Extensions/Example-16.md)

This example combines the functionality of copying specific file types and renaming files to avoid overwrites. It filters files by .xlsx and .txt extensions and ensures that if a file with the same name already exists in the destination folder, a new filename is generated to prevent overwriting.

### 1.3.2 Copying Files Based on Name Patterns

In this section, we delve into more advanced file copying scenarios where the selection of files is based on specific conditions such as name patterns. This approach allows for greater flexibility and precision in managing file copying tasks. The following examples showcase how to copy files that meet specific naming criteria, with added checks to handle potential issues such as overwriting existing files and handling subfolders.

### Copying Files Based on Specific Prefixes

### [Copying Files That Start with Specific Characters](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-17.md)

This example demonstrates how to copy files from a source directory to a destination directory based on whether their names start with the characters "Al". The script iterates over the files in the source directory and copies those that match the condition to the destination folder.

### [Copying Files That Start with Specific Characters and Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-18.md)

This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

### [Copying Files (Excluding Subfolders) That Start with Specific Characters](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-19.md)

In this example, the script is enhanced to exclude subfolders from the copy operation. 


### [Copying Files (Excluding Subfolders) That Start with Specific Characters and Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-20.md)

This example combines the enhancements from previous examples. It excludes subfolders from the copy operation and handles potential overwrites by generating new filenames with incremental suffixes if a file with the same name already exists in the destination folder.

### Copying Files Based on Specific Suffix

### [Copying Files That End with Specific Characters](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-21.md)

This example demonstrates how to copy files from a source directory to a destination directory based on whether their base names (excluding extensions) end with the characters "_gl". The script iterates over the files in the source directory and copies those that match the condition to the destination folder.

### [Copying Files That End with Specific Characters and Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-22.md)

This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

### [Copying Files (Excluding Subfolders) That End with Specific Characters](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-23.md)

In this example, the script is enhanced to exclude subfolders from the copy operation. It only processes and copies files that end with the specified characters.

### [Copying Files (Excluding Subfolders) That End with Specific Characters](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-24.md)

In this example, the script is enhanced to exclude subfolders from the copy operation. It only processes and copies files that end with the specified characters.

### Copying Files Based on Specific Keywords

### [Copying Files That Contain Specific Keywords](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-25.md)

This example demonstrates how to copy files from a source directory to a destination directory based on whether their base names (excluding extensions) contain the keyword "Al". The script iterates over the files in the source directory and copies those that match the condition to the destination folder.

### [Copying Files That Contain Specific Keywords and Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-26.md)

This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

### [Copying Files (Excluding Subfolders) That Contain Specific Keywords](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-27.md)

In this example, the script is enhanced to exclude subfolders from the copy operation. It only processes and copies files that contain the specified keyword, ensuring that no subfolders are mistakenly copied.

### [Copying Files (Excluding Subfolders) That Contain Specific Keywords and Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Name_Patterns/Example-28.md)

This example combines the enhancements from previous examples. It excludes subfolders from the copy operation and handles potential overwrites by generating new filenames with incremental suffixes if a file with the same name already exists in the destination folder.

### Copying Files Based on Specific Keywords and Extensions

This subsection focuses on scripts that copy files from a source directory to a destination directory based on specific keywords within the file names and particular file extensions. The examples provided demonstrate how to handle various scenarios such as files starting or ending with a certain keyword, or containing a keyword, and ensuring the file has a specified extension (e.g., ".xlsx"). Additionally, some examples incorporate methods to avoid overwriting existing files in the destination directory by generating unique filenames when conflicts arise. These scripts are useful for organizing files, creating backups, and managing data based on specific naming conventions and file types.

### [Copying Files That Start with a Specific Keyword and Have a Specific Extension](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Specific_Keywords_and_Extensions/Example-29.md)
This script copies files from a source directory to a destination directory if their names start with "Al" and have a ".xlsx" extension. It iterates over the files in the source directory and copies those that match the conditions to the destination folder.

### [Copying Files That Start with a Specific Keyword and Have a Specific Extension, Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Specific_Keywords_and_Extensions/Example-30.md)
This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

### [Copying Files That End with a Specific Keyword and Have a Specific Extension](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Specific_Keywords_and_Extensions/Example-31.md)
This script copies files from a source directory to a destination directory if their base names end with "_Al" and have a ".xlsx" extension. It ensures that only files matching these criteria are copied.

### [Copying Files That End with a Specific Keyword and Have a Specific Extension, Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Specific_Keywords_and_Extensions/Example-32.md)

This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

### [Copying Files with a Specific Extension and Containing a Specific Keyword](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Specific_Keywords_and_Extensions/Example-33.md)
This script copies files from a source directory to a destination directory if their names contain the keyword "Al" and have a ".xlsx" extension. It ensures that only files matching these criteria are copied.

### [Copying Files with a Specific Extension and Containing a Specific Keyword, Handling Overwrites](https://github.com/Umersaeed81/File_Management_Operations/blob/main/Copying_Files_Based_on_Specific_Keywords_and_Extensions/Example-34.md)
This example builds on the previous one by adding functionality to handle potential overwrites. If a file with the same name already exists in the destination folder, the script generates a new filename with an incremental suffix to avoid overwriting the existing file.

![](https://github.com/Umersaeed81/File_Management_Operations/blob/main/log/pic1.png?raw=true)





