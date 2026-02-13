# Oracle PDB Management Assignment

## Student Information
- **Name: INGABIRE NADDY 29003
- **Student ID: 29003
- **Course:** INSY 8311 - Database Development with PL/SQL
- **Date:** February 13, 2026

---

## Overview

Hands-on Oracle Multitenant Architecture assignment demonstrating PDB creation, deletion, user management, and OEM dashboard access.

---

## Oracle Environment
- **Database:** Oracle 21c Express Edition (21.3.0.0.0)
- **OS:** window 11
- **Tools:** SQL*Plus, Oracle Enterprise Manager

---

## Task 1: Create Main PDB

**PDB Created:** '[NA_pdb_29003]'
**Username:** `[NADDY_PLSQLAUCA_29003]`

**Commands:**
```sql
CREATE PLUGGABLE DATABASE [pdb_name]
ADMIN USER [NADDY] IDENTIFIED BY [12345]
FILE_NAME_CONVERT = ('pdbseed', '[pdb_NA_pdb_29003]');

ALTER PLUGGABLE DATABASE [pdb_NA_pdb_29003] OPEN;
GRANT CONNECT, RESOURCE, DBA TO [NADDY_PLSQLAUCA_29003];
```

**Evidence:** Screenshots show PDB creation, open state (READ WRITE), and user verification.<img width="886" height="789" alt="create pdb" src="https://github.com/user-attachments/assets/26ee684f-7437-46df-9ca5-c72ef0c5e17b" />
<img width="846" height="331" alt="pdb open" src="https://github.com/user-attachments/assets/b9dc0ea4-8dfd-4ae8-ba97-398e1cc85438" />
<img width="883" height="293" alt="user exit" src="https://github.com/user-attachments/assets/86105dfe-d448-4bd9-8638-de910a60dc5a" />




---

## Task 2: Create and Delete Temporary PDB

**Temp PDB:** `[NA_pdb_29003]`

**Commands:**
```sql
CREATE PLUGGABLE DATABASE [NA_pdb_29003]
ADMIN USER NA_admin IDENTIFIED BY [12345]
FILE_NAME_CONVERT = ('pdbseed', '[temp_pdb_name]');

ALTER PLUGGABLE DATABASE [NA_pdb_29003] CLOSE IMMEDIATE;
DROP PLUGGABLE DATABASE [NA_pdb_29003] INCLUDING DATAFILES;
```

**Evidence:** Screenshots show creation, both PDBs existing, deletion, and verification.
<img width="857" height="516" alt="drop pdb" src="https://github.com/user-attachments/assets/ef70ae8f-7dcb-4473-a34d-b0f4c14443d2" />
<img width="877" height="798" alt="both pdbs" src="https://github.com/user-attachments/assets/16435409-4c94-402e-b8bd-5bcefd13e040" />
<img width="883" height="801" alt="verify delusion" src="https://github.com/user-attachments/assets/407e61de-a412-4ba7-a6e8-ca2da6d70927" />

---

## Task 3: Oracle Enterprise Manager

**Access:** https://localhost:5500/em (SYS as SYSDBA)

**Evidence:** OEM dashboard screenshot showing PDB status and username.<img width="1893" height="874" alt="oem darshbord" src="https://github.com/user-attachments/assets/483f8259-ca9a-4d52-a17b-6c45a78f6ec5" />


---

## Challenges and Solutions

**Issue:** "Insufficient privileges" error when opening PDB  
**Solution:** Reconnected as SYSDBA using `sqlplus / as sysdba`  
**Learning:** Always verify SYSDBA connection for administrative tasks

---

## Repository Structure
```
oracle_pdb_ass_II_[studentId]_[firstname]/
├── README.md
└── screenshots/
    ├── task1_pdb_creation.png
    ├── task1_pdb_open.png
    ├── task1_user_verification.png
    ├── task2_temp_creation.png
    ├── task2_both_pdbs.png
    ├── task2_deletion.png
    └── task3_oem_dashboard.png
```

---

## Academic Integrity Statement

I, **[INGABIRE NADDY]** (ID: **[29003]**), declare this work is completed individually. All commands, screenshots, and documentation are my own. No AI tools or collaboration were used.

**Signed:** [INGABIRE NADDY]  
**Date:** [1/FEBRUARY/2026]

---

## Submission
- **Repository:** PUBLIC ✓
- **Main PDB:** []
- **Status:** Complete
