# Oracle PDB Assignment II

## Overview
This repository documents the completion of Assignment II, covering Oracle 
Multitenant architecture: creating a pluggable database (PDB), creating a 
user inside it, creating and deleting a temporary PDB, and reviewing the 
Oracle environment's configuration and status.

## Oracle Environment Used
- Oracle AI Database 26ai Free (Release 23.26.3.0.0), native installation on Windows
- Connected via SQL*Plus

## Explanation of Each Task

### Task 1: Create a New Pluggable Database
Created PDB `EL_PDB_20251IMA004` from the CDB root, opened it in READ WRITE 
mode, and created user `elyse_plsqlauca_20251IMA004` inside it with CONNECT, 
RESOURCE, and DBA privileges and an unlimited quota on the USERS tablespace.

### Task 2: Create and Delete a PDB
Created a temporary PDB `EL_TO_DELETE_PDB_20251IMA004`, verified it existed 
and was open, then closed it with `CLOSE IMMEDIATE` and dropped it with 
`INCLUDING DATAFILES`. Confirmed deletion via an empty query result against 
`v$pdbs`.

### Task 3: Oracle Enterprise Manager (OEM) Setup
Oracle Enterprise Manager Database Express (EM Express) is desupported in 
Oracle AI Database 26ai. In its place, this section documents the Oracle 
environment directly via SQL*Plus: database version, the full list of 
containers/PDBs with their open modes, confirmation of the created user 
inside the PDB, instance status, and core tablespace status — equivalent 
information to what an OEM dashboard would display.

### Task 4: Documentation & Reporting
This README and the accompanying screenshots in `screenshots/` document 
all completed work.

## Challenges Faced
- The newly created PDB did not initially have a USERS tablespace, causing 
  an ORA-00959 error when granting a quota. Resolved by creating the 
  tablespace manually with `CREATE TABLESPACE users DATAFILE SIZE 100M 
  AUTOEXTEND ON NEXT 10M MAXSIZE UNLIMITED;` before retrying the grant.
- Oracle Enterprise Manager Database Express (EM Express) returned a 
  "Not Implemented" error when accessed, because it has been desupported 
  in Oracle AI Database 26ai. Substituted a SQL*Plus-based environment 
  summary covering the same information (version, PDB list, user, 
  instance status, tablespace status).

## Integrity Statement
This work is my own. All commands were run and verified on my own Oracle 
installation, and all screenshots reflect my own environment.

## Submission Details

Repository Link: [paste your GitHub repo URL here]
PDB Name Created: el_pdb_20251IMA004
Issues Encountered: Yes# oracle_pdb_ass_II_20251IMA004_elyse
