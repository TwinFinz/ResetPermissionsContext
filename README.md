# Reset Permissions Context Menu - Windows Registry Modification  

## Overview  
This registry modification adds a **"Reset Permissions"** option to the right-click context menu for files, folders, and drives. When selected, it resets NTFS permissions using the `icacls` command with **verbose output** (displays processing details).  

## Features  
✅ Adds a right-click option for **files, folders, and drives**.  
✅ Uses **icacls** to reset permissions recursively.  
✅ Runs with **elevated privileges** (admin rights required).  
✅ Provides **verbose output** (displays progress instead of running silently).  

## Installation  
1. **Download** the `Add_Reset_Permissions_to_context_menu.reg` file.  
2. **Double-click** the file to merge it into the Windows Registry.  
3. Click **Yes** when prompted by UAC.  
4. Click **OK** to confirm.  

## Usage  
1. **Right-click** any file, folder, or drive. (Windows 11 may require Shift+Right Click)
2. Select **"Reset Permissions"** from the context menu.  
3. A command window will appear and show the progress of the permission reset.  

## Uninstallation  
To remove the "Reset Permissions" option:
1. **Download** the `Remove_Reset_Permissions_to_context_menu.reg` file.  
2. **Double-click** the file to merge it into the Windows Registry.  
3. Click **Yes** when prompted by UAC.  
4. Click **OK** to confirm.  

To remove the "Reset Permissions" option manually:  
1. Open **Registry Editor** (`regedit`).  
2. Navigate to:  
   - `HKEY_CLASSES_ROOT\*\shell\ResetPermissions`  
   - `HKEY_CLASSES_ROOT\Directory\shell\ResetPermissions`  
   - `HKEY_CLASSES_ROOT\Drive\shell\ResetPermissions`  
3. Delete the `ResetPermissions` keys from all three locations.  

Alternatively, you can create a `.reg` file with the following content and merge it to remove the modifications:  

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\*\shell\ResetPermissions]
[-HKEY_CLASSES_ROOT\Directory\shell\ResetPermissions]
[-HKEY_CLASSES_ROOT\Drive\shell\ResetPermissions]
```
