VMware Vcenter Appliance 5.5+ Database Archiving tool
==========================
### Backup/restore database archives of your Vcenter Appliance PostGres and Inventory Services.
### You can use this script to schedule backups and archive maintenance.
Copyright (c) 2015 Jon Retting

`git@github.com:jonretting/vcdb-tool.git`

Version: 0.21

### Release Notes:

#### 0.21:
- Print out the name and size of the new Invetory Backup archive after backup success

#### 0.2:
- Can backup Inventory Service Database and restore it
- Ability to list contents of backup directory
- made the serialization of file names more legible
- various tweaks

#### 0.1:
- Initial release

INFO:
-----
- Tested on Vcenter Appliance 5.5d and 5.5e
- Works only on an embedded local Postgres Database
- When using the "-p" purge option a value of "30" would delete all archives over 30 days old
- Edit "vcdbt_backup_dest" variable to change backup destination path

OPTIONS:
--------
    vcdb-tool [-e] [-i=file] [-p=#]
    -e    Export a backup archive to the backup path
    -i    Import the specified backup file from the backup path (-i file.bak)
    -b    Backup the Inventory Service database
    -r    Restore an Inventory Service database archive (-r file.bak)
    -l    List contents of archive folder
    -p    Purge outdated backup archives older than # days (-p 30)
    -h    this cruft

EXAMPLES:
---------
- Run a PostGres Database Export
    `./vcdb-tool -e`

- Run a PostGres Database Import
    `./vcdb-tool -i VCDB.db.042615.1430061195.bak`

- Run an Inventory Service Backup
    `./vcdb-tool -b`

- Run an Inventory Service Restore
    `./vcdb-tool -r  inv-backup.042615.1430061173.bak`

- List archive folder contents
    `./vcdb-tool -l`

- Cleanup old backup archives older than thirty days
    `./vcdb-tool  -p 30`

Based on official VMware http://kb.vmware.com/kb/2062682 and http://kb.vmware.com/kb/2062682