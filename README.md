# Data-Extractor-and-backup
This batch file automates the process of backing up specific user directories (such as Pictures, Favorites, Videos, Downloads, Desktop, Music, and Documents) from the user profile to a target drive.

# Functionality
Backup Directories: The script uses the xcopy command to copy all the contents from the user's profile folders (such as Pictures, Favorites, Videos, etc.) to a specified destination drive.
Incremental Backup: It only copies new or modified files, skipping files that haven't changed.
Hidden and System Files: The script ensures that hidden and system files are copied as well.
File Attributes and Permissions: It maintains file attributes, permissions, and timestamps during the copy process.
# Key Commands Used
SET odrive: Retrieves the system's drive letter and stores it in the variable %odrive%.
xcopy: This is the core command used to copy files and folders. The flags used include:
/s: Copies directories and subdirectories, except empty ones.
/c: Continues copying even if errors occur.
/d: Copies only files that have been changed.
/e: Copies all subdirectories, including empty ones.
/h: Copies hidden and system files.
/i: Assumes the destination is a directory if it's not clear.
/r: Overwrites read-only files.
/y: Suppresses prompting when overwriting files.
/g: Copies files without altering the encryption status.

# Usage
Ensure the Destination Drive is Correct: The script uses %drive% as the destination where backups will be stored. Modify this variable to point to your backup drive (e.g., D:\, E:\, etc.).
Run the Script: Simply double-click the .bat file to execute the backup process. You can also schedule this batch file using Task Scheduler for periodic backups.

Example:
# batch
Copy code
%backupcmd% "%USERPROFILE%\pictures" "D:\backups\My pics"
This line copies the Pictures directory from the current user profile to the D:\backups\My pics directory.

Supported Directories
Pictures: %USERPROFILE%\pictures
Favorites: %USERPROFILE%\Favorites
Videos: %USERPROFILE%\videos
Downloads: %USERPROFILE%\Download
Desktop: %USERPROFILE%\Desktop
Music: %USERPROFILE%\Music
Documents: %USERPROFILE%\Documents
# Customization
You can easily modify the directories or destination paths by editing the paths in the script to suit your backup needs.
# Disclaimer
This is for educational purposes only
