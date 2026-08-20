#### **The File System**
- Installation's file system can be checked by checking the properties of the drive the OS is installed on <- Typically the C drive (`C:\`)
- **New Technology File System (NTFS)** <- File system used in modern Windows Versions
	- Replaced **File Allocation Table (FAT16/FAT32)** and **High Performance File System (HPFS)**
		- FAT partitions still used today, typically in USB devices, MicroSD cards, etc.
			- Not traditionally used on Windows PCs/Laptops or Windows Servers anymore
	- NTFS is known as a **journaling file system** <- can **automatically repair** the files/folders on disk using information stored in a **log file**. -> Not possible with FAT
	- NTFS addresses lot of the limitations of previous file systems such as:
		- Supports file larger than 4GB
		- Set specific permissions on files and folders
		- Folder and File Compression
		- Encryption (Encryption File System (EFS))

###### **NTFS Permissions**
-  **Read**:
	- Folders - viewing and listing of file and subfolders
	- Files - Viewing or accessing of file's contents

- **Write**:
	- Folders - Adding of files and subfolders
	- Files - Writing to a file

- **Read and Execute**:
	- Folders - Viewing and listing of file and subfolders, executing of files; inherited by files and folders
	- Files - Viewing and accessing of file's contents, executing of the file

- **List Folder Contents**:
	- Folders - Viewing and listing of files and subfolders, executing of files; inherited by folders only
	- Files - N/A

- **Modify**:
	- Folders - Reading and writing of files and subfolders; deletion of the folder
	- Files - Reading and writing of file; deletion of the file

- **Full Control**:
	- Folders - Reading, Writing, Changing, and deletion of files and subfolders
	- Files - Reading, Writing, Changing, and deletion of the file

- Permissions can be viewed in the **security** tab of the **Properties Menu** for a file/folder

###### **Alternate Data Stream (ADS)**
- **Allows files to contain more than one stream of data**
	- 3rd party executables can be used to view this data
	- PowerShell also allows ADS for files to be viewed
- Every file has at least **one data stream** (`$DATA`)
	- `:$DATA` = Default data stream of every NTFS file, it contains the normal file contents and **is not** an ADS
- File attribute specific to Windows NTFS
- Example usage of ADS = Identifiers written to ADS to identify that a file was downloaded from the internet
- Malware writers have to use ADS to hide data 

#### **The Windows/System32 Folders**
- **Windows Folder** (`C:\Windows`) is traditionally known as the folder which **contains the Windows OS**
	- Not necessary to store in the C drive or technically even in the Windows folder at all
- Where **environment variables**, specifically system environment variables, become relevant
	- Environment Variables -> Store info about the OS environment, including details such as: OS path, number of processors used by the OS, and the location of temp folders
	- System environment variable for Windows directory is `%Windir%`
- **System32** is one such folder stored within the **Windows Folder**
	- System32 - Stores important files which are critical for the OS
	- **Interaction with System32 should be handled with extreme caution**
		- Deleting any files or folders within can render the Windows OS inoperational