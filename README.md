# Folder Synchronization Script

## Overview

This PowerShell script synchronizes the contents of two folders: a source folder and a replica folder. The script ensures that the replica folder mirrors the source folder, including creating new files, updating existing files, and removing files that are no longer present in the source folder. All operations are logged to both a file and the console.

## Requirements

- PowerShell version 5.1 or higher
- Access to both the source and replica folders
- Permissions to read from and write to the specified folders and log file

## Parameters

- `-SourceFolder`: The path to the source folder that you want to synchronize.
- `-ReplicaFolder`: The path to the target replica folder where the synchronized files will be copied.
- `-LogFile`: The path to the log file where synchronization operations will be recorded.

## Usage

To run the script, open PowerShell and execute the script with the required parameters. For example:

```powershell
.\SyncFolders.ps1 -SourceFolder "C:\Path\To\Source" -ReplicaFolder "C:\Path\To\Replica" -LogFile "C:\Path\To\LogFile.txt"
```

## Functionality

1. **Initialization**: 
   - The script checks if the specified log file exists. If it does not, it creates a new empty log file.

2. **Logging**:
   - The script starts logging both to the console and to the log file using `Start-Transcript`.

3. **Synchronization**:
   - The script recursively reads the source and replica folders.
   - It copies files from the source to the replica if they do not exist or have been updated.
   - It removes files from the replica that are no longer present in the source.

4. **Completion**:
   - The script stops logging using `Stop-Transcript` when the synchronization is complete.

## Notes

- Ensure that the source and replica paths are correct and that you have the necessary permissions to read from and write to these directories.
- The script will overwrite files in the replica folder if they are different from those in the source folder.
- Any errors or issues during the script execution will be logged to the specified log file for review.