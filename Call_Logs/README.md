# Call Logs

This folder contains files, documentation, screenshots, and analysis related to mobile device call-log artifacts.


Call Logs Analysis

Objective: Examine Call Log artifacts for communication records.

Method:

Identify the Android call activity database.
Inspect the database schema.
Query Call Logs records.
Convert Android/Unix timestamps into human-readable dates.
Correlate caller /callee information.

Analysis note:
The call activity database was examined as part of the mobile-device forensic workflow. Where database records were unavailable or inaccessible in Kali Linux because of Android permissions and file paths, they were accessible and recovered on the Windows command terminal

Forensic significance:
Call activity database records can provide communication timelines and relationships between phone numbers, but their evidentiary value depends on the database's completeness and the preservation of associated WAL/journal files.

