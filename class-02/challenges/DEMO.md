# Ops Challenge - Append; Date and Time

## Demo Code

The demo code below introduces concepts necessary to complete the challenge.

```bash
#!/bin/bash

# Script:                       Ops 301 Ops Chall 02
# Purpose:                      Append, date and time

# How to show time and date

# Running date command from terminal gives a general output

# Here we assign variables but you can run these commands on their own without the ` outside the command string. These are modifiers shown.

year=`date +%Y`
month=`date +%m`
day=`date +%d`
hour=`date +%H`
minute=`date +%M`
second=`date +%S`
echo `date`
echo "Current Date: $day-$month-$year"
echo "Current Time: $hour:$minute:$second"

# How to row append

# First create a file testfile.txt and add some lines to it.

echo "Original file before append:"
cat testfile.txt

# The >> double carrot here will row append

echo "New string" >> testfile.txt
echo "Appended file:"
cat testfile.txt

```
