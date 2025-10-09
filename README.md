# oracle-database-assignment
# oracle-database-assignment
Oracle Database Task Report

Student Name: TETA HUGUETTE

Student ID: 28982

Course: PL/SQL DATABSE DEVELOPMENT

Assignment: Database Creation, Deletion, and OEM Configuration


Overview of Tasks

Task 1: Create a New Pluggable Database (PDB)

Created a PDB named: hu_pdb_28982

Created a user to store class work: huguette_plsqlauca_28982

Password: teta(simple password chosen)

Verified that the database was OPEN by ; 

SQL> select status from v$instance;
-----------------------------------------------------------
Task 2: Create and Delete a PDB

Created a second PDB named: hu_to_delete_pdb_2025108

Verified creation using:

SHOW pdbs;

Deleted the second PDB after verification:

SQL> DROP PLUGGABLE DATABASE hu_to_delete_pdb_28982 INCLUDING DATAFILES;

Screenshots were taken for both creation and deletion.
-----------------------------------------------------------
Task 3: Configure Oracle Enterprise Manager (OEM)

I configured Oracle Enterprise Manager (OEM) to manage and monitor my pluggable databases.
After completing Tasks 1 and 2

I accessed the OEM dashboard and  my database appeared with my username.

✅ Conclusion

All three tasks (creation, deletion, and OEM setup) were completed successfully using Oracle 19c.
All commands were tested in SQL*Plus and verified via screenshots.
