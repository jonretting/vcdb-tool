VMware Vcenter Appliance 5.5+ Postgre SQL Database Archiving tool
==========================
### Capable of creating backup archives of your VC Database, and import backup archives.
### You can use this script to schedule backups and archive mantainence.
Copyright (c) 2015 Jon Retting

`git@github.com:jonretting/vcdb-tool.git`

INFO:
-----
- Tested on Vcenter Appliance 5.5d and 5.5e
- Works only on an embended local Postgre Database
- When using the "-p" purge option a value of "30" would delete all arvhives over 30 days old
- Edit "vcdbt_backup_dest" variable to change backup destination path

OPTIONS:
--------
    vcdb-tool [-e] [-i=file] [-p=#]
    -e    Export a backup archive to the backup path
    -i    Import the specified backup file from the backup path (-i file.bak)
    -p    Purge outdated backup archives older than # days (-p 30)
    -h    this cruft

EXAMPLES:
---------
- Run an Export
    `./vcdb-tool -e`

- Run an Import
    `./vcdb-tool -i VCDB.0421151429615949.bak`

- Cleanup old backup archives older than thirty days
    `./vcdb-tool  -p 30`