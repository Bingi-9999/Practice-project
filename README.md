# Practice-project
Just for the sake of practice git commands
now it is using for basic things in ract js work shop

set wsc = CreateObject("WScript.shell")
Do
WScript.Sleep (60*1000)
wsc.SendKeys ("{SCROLLLOCK 2}")
Loop


DB2 Setup log file started at:  Mon Mar 04 09:32:26 AM 2024 UTC
============================================================
 
Operating system information: Linux 4.18.0-513.11.1.el8_9.x86_64.#1 SMP Thu Dec 7 03:06:13 EST 2023 x86_64
 
 
New instances:
    Instance name:                              db2inst1
        Instance user information:
            User name:                          db2inst1
        Fenced user information:
            User name:                          db2fenc1
 
 
 
Setting default global profile registry variables :.......Success
The maximum number of logical nodes was not specified for the instance
"db2inst1". Default parameters will be used.
 
Initializing instance list :.......Success
ERROR:        Program name = db2idbm
Instance home dir = /home/db2inst1,   Sysadm group = db2iadm1
Instance type = 1,  Auth type = server
 
SQL6031N  Error in the db2nodes.cfg file at line number "0".  Reason code
"11".
Update DBM cfg SYSADM_GROUP errcode = 8
>>>>> Error message = SQL6031N  Error in the db2nodes.cfg file at line number "0".  Reason code
"11". <<<<<
DBI1703E  No valid service name or port number found.
 
Explanation:
 
No valid service name or port number for this instance can be found in
the TCP/IP services file. This information is either missing or is
invalid.
 
If you installed "DB2 Extended Server Edition" product, a service name
must be specified for the instance before using this command.
 
User response:
 
Specify valid service name and port number for this instance and enter
this command again.
 
 
ERROR: An error occurred while configuring the instance "db2inst1".
 
Configuring DB2 instances :.......Failure
Updating global profile registry :.......Success
 
Post-installation instructions
-------------------------------
 
Required steps:
There were some errors detected during DB2 installation. To collect the information files from the system, run the "db2support -install" command with the proper options before reporting the problem to IBM service. For information regarding the usage of the db2support tool, check the DB2 Information Center.
 
Optional steps:
To validate your installation files, instance, and database functionality, run the Validation Tool, /opt/ibm/db2/V11.5/bin/db2val. For more information, see "db2val" in the DB2 Information Center.
 
Verify that you have access to the DB2 Information Center based on the choices you made during this installation. If you performed a typical or a compact installation, verify that you can access the IBM Web site using the internet. If you performed a custom installation, verify that you can access the DB2 Information Center location specified during the installation.
 
Ensure that you have the correct license entitlements for DB2 products and features installed on this machine. Each DB2 product or feature comes with a license certificate file (also referred to as a license key) that is distributed on an Activation CD, which also includes instructions for applying the license file. If you purchased a base DB2 product, as well as, separately priced features, you might need to install more than one license certificate. The Activation CD for your product or feature can be downloaded from Passport Advantage if it is not part of the physical media pack you received from IBM. For more information about licensing, search the Information Center (https://www.ibm.com/docs/en/db2/11.5) using terms such as "license compliance", "licensing" or "db2licm".
 
To use your DB2 database product, you must have a valid license. For information about obtaining and applying DB2 license files, see http://www-01.ibm.com/support/knowledgecenter/SSEPGG_11.1.0/com.ibm.db2.luw.qb.server.doc/doc/c0061199.html.
 
 
DB2 Setup log file finished at:  Mon Mar 04 09:33:35 AM 2024 UTC
============================================================
