# Oracle Database PDB Management Assignment


- **Name:** Lisa Ornella UWASE
- **Student ID:** 28753
- **Username:** lisa_plsqlauca_28753
- **Database:** Oracle 21c XE
- **Lecture:**Eric

## Assignment Overview
This project demonstrates the creation and management of Pluggable Databases (PDBs) in Oracle Database, 
including configuration of Oracle Enterprise Manager (OEM).

## Tasks Completed

###  Task 1: Create Main PDB
- Created PDB: `plsql_class2025db`
- Admin User: `lisa_plsqlauca_28753`

###  Task 2: Create and Delete Temporary PDB
- Created PDB: `li_to_delete_pdb_28753`
- Admin User: `lisa_temp_admin`


### Task 3: Oracle Enterprise Manager Configuration
- OEM Access: Successfully configured and accessible
- URL: `https://localhost:5500/em`

## Screenshots

### Task 1 - PDB Creation
![PDB Creation](screenshots/pdb_creation.png)

### Task 2 - PDB Deletion
![PDB Deletion](screenshots/pdb_deletion.png)

### Task 3 - OEM Dashboard
![OEM Dashboard](screenshots/oem_dashboard.png)

## SQL Commands Used

### Create Main PDB
```sql
CREATE PLUGGABLE DATABASE plsql_class2025db
ADMIN USER lisa_plsqlauca_28753 IDENTIFIED BY password
ROLES=(DBA)
FILE_NAME_CONVERT=('C:\APP\HP\PRODUCT\21C\ORADATA\XE\PDBSEED\', 
                   'C:\APP\HP\PRODUCT\21C\ORADATA\XE\PLSQL_CLASS2025DB\');
