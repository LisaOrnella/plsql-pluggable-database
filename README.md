# Oracle Database PDB Management Assignment


- **Name:** Lisa Ornella UWASE
- **Student ID:** 28753
- **Username:** lisa_plsqlauca_28753
- **Database:** Oracle 21c XE
- **Lecture:**Eric

## Assignment Overview
This project demonstrates the creation and management of Pluggable Databases (PDBs) in Oracle Database, 
including configuration of Oracle Enterprise Manager (OEM).

## Tasks

###  Task 1: Create Main PDB
- Created PDB: `plsql_class2025db`
- Admin User: `lisa_plsqlauca_28753`
```sql
CREATE PLUGGABLE DATABASE plsql_class2025db
ADMIN USER lisa_plsqlauca_28753 IDENTIFIED BY password
ROLES=(DBA)
FILE_NAME_CONVERT=('C:\APP\HP\PRODUCT\21C\ORADATA\XE\PDBSEED\', 
                   'C:\APP\HP\PRODUCT\21C\ORADATA\XE\PLSQL_CLASS2025DB\');
```
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

- ![image alt](https://github.com/LisaOrnella/plsql-pluggable-database/blob/main/2ND%20DATABE%20CREATED.png?raw=true)
- ** For Deletion
  ```sql
  DROP PLUGGABLE DATABASE li_to_delete_pdb_28753 INCLUDING DATAFILES;
  ```
- ![image alt](https://github.com/LisaOrnella/plsql-pluggable-database/blob/main/drop%20plug.png?raw=true)

  ISSUES 


### Task 3: Oracle Enterprise Manager Configuration
- OEM Access: Successfully configured and accessible
- URL: `https://localhost:5500/em`
- ![image alt](https://github.com/LisaOrnella/plsql-pluggable-database/blob/main/Screenshot%202025-10-02%20110721.png?raw=true)

