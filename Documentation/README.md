# Documentation

This folder contains project documentation, methodology, procedures, technical notes, and supporting documentation.

I.	Methodology

The investigation followed a structured mobile-forensics workflow:

1.	Preparation
•	Establish investigation directories.
•	Identify the Android emulator/device.
•	Confirm ADB connectivity.
2.	Acquisition
•	Acquire application databases using ADB.
•	Store acquired artifacts inside case-specific evidence directories.
3.	Preservation
•	Calculate SHA-256 hashes for acquired evidence.
•	Maintain original evidence separately from analysis copies.
4.	Examination
•	Identify SQLite databases.
•	Inspect database schemas.
•	Identify relevant tables.
•	Execute targeted SQL queries.
5.	Analysis
•	Convert timestamps.
•	Correlate browser, messaging, email, and communication artifacts.
•	Identify relevant searches, messages, and downloaded files.
6.	Documentation
•	Record commands and outputs.
•	Document limitations and errors.
•	Produce timelines, findings and final reports.





II.	Setup / Instructions

The laboratory consisted primarily of:

•	Windows examination workstation
•	Kali Linux forensic/pentesting VM
•	Android emulator
•	Android Debug Bridge (ADB)
•	SQLite
•	Windows certutil
•	Python tooling for documentation/automation

III.	Basic acquisition workflow

Identify device
      ↓
Verify ADB connection
      ↓
Identify application package
      ↓
Locate application databases
      ↓
ADB acquisition
      ↓
Hash evidence
      ↓
Create analysis copy
      ↓
SQLite examination
      ↓
Extract artifacts
      ↓
Timeline/correlation
      ↓
Report findings
