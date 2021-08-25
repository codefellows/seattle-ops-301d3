# Ops Challenge - File Permissions

## Demo Code

The demo code below introduces concepts necessary to complete the challenge. 

```bash
#!/bin/bash

# Script:                       Ops 301 Ops Chall ##
# Author:                       Your Name
# Date of latest revision:      MM/DD/YYYY
# Purpose: xxx

# How to view file permissions

ls -al

# Add file name if you want to filter the view

ls -al testfile.txt

# How to set file permissions to a single file

chmod 777 testfile.txt

# How to set file permissions on this directory and all its contents

chmod -R 755 ./

# or use --recursive

chmod --recursive 755 ./

```
