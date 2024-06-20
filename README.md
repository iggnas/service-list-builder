# Note
This is an archive of amits service list builder. I do not own anything in this repo

# service-list-builder

I am not responsible for damage caused to computer. This tool is powerful and for advanced users only. There is a risk of damaging your operating system if you disable core services that are required for Windows to function correctly. It is your responsibility to use suitable service configurations for your specific operating system. It is also recommended that you use this tool before installing any programs as any other services not defined in the lists will be disabled (e.g. services installed by anticheats, or you could simply enable them after building the scripts, but the first method is recommended). If you would like to rebuild the scripts, ensure to run the generated Services-Enable.bat script beforehand as the tool relies on the current state of services for building future scripts.

# Usage and Program Logic

-    Download files from releases

-    Open lists.ini in a text editor

   - Note: All entries are case-sensitive

   - Every user mode service NOT specified in the [enabled_services] section will get disabled. These two sections act as whitelist of user mode services NOT to disable

   - Individual services to disable can be explicitly specified in the [individual_disabled_services] section. This section does not follow the disable all except logic. Only the services specified in this section will get disabled. This is useful in situations where the user only needs to disable a few user mode services instead of using the batch approach with          [enabled_services] or would like to disable kernel mode services at all

   - Paths to folders or binaries can be specified in the [rename_binaries] section. The logic behind this is that when a binary gets renamed to anything other than its original file name, it will not run. Avoid folders and binaries with # in the name due to conflict with inline comments

   - Pass lists.ini as an argument to the program through the command-line with the command below to build the scripts
```
    service-list-builder.exe --config lists.ini
```
   - The scripts will be built in the build folder. NSudo is required to run the scripts with Enable All Privileges checkbox enabled to prevent errors when writing to registry and renaming files
