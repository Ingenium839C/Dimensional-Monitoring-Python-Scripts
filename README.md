# Dimensional-Monitoring-Python-Scripts
Python files for the Raspberry Pi are here. Although these files can also already be found on the Raspberry Pi under the directory: "/home/willh/Documents/Ingenium".

## _**Raspberry Pi Login Details**_:

**Hostname:** 839C.local

**Username:** 839C

**Password:** 292629Will

## _**README for automaticEmailSender.py:**_

Line 13: email_receivers = ['dimensionmonitoring839c@gmail.com', 'recipent@example.com']  # List of recipients

This is where any receivers of the data can be edited. 
Since data is sent through email, each receiver's email should be written here.

Line 16: file_path = "/home/willh/Documents/Ingenium/sensorData.xlsx"

This is the specification for the file path of the spreadsheet file. 
In a Raspberry Pi this should be the absolute file path, and should match the file path used in the dataAppender.py script. 
Note that dataAppender.py will automatically create a spreadsheet file if none exist at the file path, so the file path in automaticEmailSender.py simply needs to match that in dataAppender.py, and the parent folders should exist.


## _**README for dataAppender.py:**_

Line 16: file_path = "/home/willh/Documents/Ingenium/sensorData.xlsx"

This is the specification for the file path of the spreadsheet file. 
In a Raspberry Pi this should be the absolute file path, and should match the file path used in the dataAppender.py script. 
Note that dataAppender.py will automatically create a spreadsheet file if none exist at the file path, so the file path in automaticEmailSender.py simply needs to match that in dataAppender.py, and the parent folders should exist.

Lines 29-34:

This is where the data to be appended into the spreadsheet is set.
Currently, since the Raspberry Pi was unable to connect to the sensor via I2C, the code here uses random numbers for placeholder values.
Set the variable "data" to the value of the data you want to append to the spreadsheet, replacing the code within these lines (since it sets data to random numbers).


## _**README for crontab scheduling:**_

To edit the crontab, type the following command into the Raspberry Pi terminal: 
crontab -e

When in the crontab, python scripts are scheduled by the following format:
m h dom mon dow /usr/bin/python3 /absolute/path/to/script/

The Raspberry Pi will already have commented out lines scheduling the two scripts, automaticEmailSender.py and dataAppender.py to run every minute.
To edit how often the scripts are run, edit the 5 asterisks to specify how often you want the scripts ran.
More information and help on scheduling cron jobs can be found here: https://crontab.guru

Uncomment the lines by removing the hashtag to start the scheduled scripts.
