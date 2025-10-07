# Oracle Database PDB Management Assignment


- **Name:** Lisa Ornella UWASE
- **Student ID:** 28753
- **TUESDAY CLASS GROUP B**
- **Username:** lisa_plsqlauca_28753
- **Database:** Oracle 21c XE
- **Lecture:** Eric Maniraguha

## Assignment Overview
This project demonstrates the creation and management of Pluggable Databases (PDBs) in Oracle Database, 
including configuration of Oracle Enterprise Manager (OEM).

## Tasks

###  Task 1: Create Main PDB
- Created PDB: `plsql_class2025db`
- Admin User: `lisa_plsqlauca_28753`
  
```sql
SQL*Plus: Release 21.0.0.0.0 - Production on Mon Oct 6 17:23:39 2025
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.

Enter user-name: system
Enter password:
Last Successful login time: Sun Oct 05 2025 22:33:10 +02:00

Connected to:
Oracle Database 21c Express Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0


CREATE PLUGGABLE DATABASE plsql_class2025db
ADMIN USER lisa_plsqlauca_28753 IDENTIFIED BY password
ROLES=(DBA)
FILE_NAME_CONVERT=('C:\APP\HP\PRODUCT\21C\ORADATA\XE\PDBSEED\', 
                   'C:\APP\HP\PRODUCT\21C\ORADATA\XE\PLSQL_CLASS2025DB\');
```

**Screenshot of creating Pluggable database**

-![image alt]( https://github.com/LisaOrnella/plsql-pluggable-database/blob/main/CREATE%20DATABASE.png?raw=true)

###  Task 2: Create and Delete Temporary PDB
- Created PDB: `li_to_delete_pdb_28753`
- Admin User: `lisa_temp_admin`
  
```sql
CREATE PLUGGABLE DATABASE li_to_delete_pdb_28753
ADMIN USER lisa_temp_admin IDENTIFIED BY temp123
ROLES=(DBA)
FILE_NAME_CONVERT=('C:\APP\HP\PRODUCT\21C\ORADATA\XE\PDBSEED\', 'C:\APP\HP\PRODUCT\21C\ORADATA\XE\LI_TO_DELETE_PDB_28753\');
``` 

 **Screenshot of creating second Pluggable database** 
 
 ![image alt](https://github.com/LisaOrnella/plsql-pluggable-database/blob/main/2ND%20DATABE%20CREATED.png?raw=true)
  
 ****Screenshot of deleting second Pluggable database****
 
  ```sql
  DROP PLUGGABLE DATABASE li_to_delete_pdb_28753 INCLUDING DATAFILES;
  ```
 ![image alt](https://github.com/LisaOrnella/plsql-pluggable-database/blob/main/drop%20plug.png?raw=true)



### Task 3: Oracle Enterprise Manager Configuration
- OEM Access: Successfully configured and accessible
- URL: `https://localhost:5500/em`
  
  ![image alt](https://github.com/LisaOrnella/plsql-pluggable-database/blob/main/Screenshot%202025-10-02%20110721.png?raw=true)

### ISSUES ENCOUNTERED

## Issues Encountered & Solutions

### 🔧 Issue 1: Insufficient Privileges for PDB Operations
- **Problem:** Received "insufficient privileges" error when trying to create and drop PDBs.
- **Solution:** Connected to the root container with SYSDBA privileges using:
  ```sql
  CONNECT sys AS SYSDBA
  ```

### 🔧 Issue 2: Finding Container Names
**Problem:** Didn't know the correct container names to switch between databases
**Solution:** Used these commands to find containers:
```sql
SHOW CON_NAME
SELECT name, con_id, open_mode FROM v$containers;
SELECT name, open_mode FROM v$pdbs;
```
### 🔧 Issue 3: PDB Not Accessible
**Problem:** PDBs created but couldn't connect to them
**Solution:** Opened PDBs after creation:
```sql
SHOW CON_NAME
SELECT name, con_id, open_mode FROM v$containers;
SELECT name, open_mode FROM v$pdbs;
```
