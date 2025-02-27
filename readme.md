# Simple Backup Script with ZIP Compression

This script allows you to back up a file or directory, compress it into a ZIP archive, and manage the retention of old backups by limiting the number of backups stored in a backup directory.

## Prerequisites

- Python 3.x
- No external libraries are required, just the Python standard library.

## Features

- **Backup a file or directory**: You can back up a single file or an entire directory.
- **ZIP Compression**: Files are compressed into ZIP format for efficient disk space usage.
- **Backup Limit**: A maximum number of backups are kept in the backup directory. Old backups are automatically deleted when the limit is reached.
- **Error Handling**: The script ensures that the file or directory to be backed up exists before proceeding and that the backup directory is created if needed.

## Configuration

Before running the script, you need to set the following parameters in the script:

1. **`OBJECT_TO_BACKUP`**: The file or directory to back up. For example:
   - `'dir'` for a directory
   - `'file.txt'` for a file
2. **`BACKUP_DIRECTORY`**: The directory where the backups will be stored.
3. **`MAX_BACKUP_AMOUNT`**: The maximum number of backups to keep in the backup directory. When this number is reached, older backups are deleted.

## How to Use the Script?

### Steps:

1. Modify the parameter values at the beginning of the script:
   - **`OBJECT_TO_BACKUP`**: Specify the file or directory to back up.
   - **`BACKUP_DIRECTORY`**: Specify the directory where you want to store the backups.
   - **`MAX_BACKUP_AMOUNT`**: Set the maximum number of backups you want to retain.

2. Run the script.

### Example Parameter Values:

```python
OBJECT_TO_BACKUP = 'dir'  # Directory to back up
BACKUP_DIRECTORY = 'backups'  # Directory where backups will be stored
MAX_BACKUP_AMOUNT = 5  # Keep a maximum of 5 backups
```

### Example Execution:

If you have a directory named `dir` and want to store the backups in a `backups` folder while keeping a maximum of 5 backups, you can configure the script as shown and run it:

```bash
python backup_script.py
```

## Script Behavior

1. **Validation of the Object to Backup**: If the file or directory does not exist, the script stops with an error message.
2. **Creating the Backup Directory**: If the backup directory does not exist, it is created automatically.
3. **Limiting the Number of Backups**: If the number of backups exceeds the maximum specified, the oldest backups are deleted.
4. **Creating the ZIP File**: The specified file or directory is compressed and stored in the backup directory with a name that includes the date and time of the backup.
5. **File and Directory Management**: The script handles both individual files and directories (including all files and subdirectories in the backup).

## Example Backup File Name

The backup file will be named as follows:
```
backup-YYYYMMDDHHMMSS-dir.zip
```
For example, a backup made on February 27, 2025, at 3:42 PM for a directory named `dir` would generate a file named:
```
backup-20250227154200-dir.zip
```

## Note

- This script is designed for simple use and can be adapted for more complex backup scenarios, such as adding email notifications, automated scheduling, etc.
