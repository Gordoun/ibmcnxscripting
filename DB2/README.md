# Some useful DB2 SQL Scripts

## setmaintenance.sh and automaint.sql

Scripts should be started as instance owner! When you call setmaintenance.sh the script:

 * generates a list of databases in the instance
 * calls automaint.sql for each database
    * activates Online- and Offline Timeframes
    * set parameters for Reorg, Backup and so on

 * YOU SHOULD: change the path of your BACKUP Directory in Line 4 of automaint.sql

## checkExID.sh

Usage:

'./checkExID.sh mailaddress'

Search mailaddress in PEOPLEDB and check the PROF_GUID column through all applications.

In some applications the mailaddress is casesensitiv on these selects, so you can decide after searching the PeopleDB, which mailaddress should be used for lookup of other applications.

## db2initscript

Copy this script to /etc/init.d/db2, it is a Script to start and stop DB2 as a service on CentOS or Red Hat.
You only have to change the PATH variables within the script.

Thanks to [Nico Meisenzahl](http://www.meisenzahl.org)
