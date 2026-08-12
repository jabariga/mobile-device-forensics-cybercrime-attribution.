# SMS Analysis

This folder contains files, screenshots, documentation, and analysis related to SMS and text-message artifacts.


 SMS Analysis

Objective: Examine SMS artifacts for communication records.

Method:

Identify the Android telephony database.
Inspect the database schema.
Query SMS records.
Convert Android/Unix timestamps into human-readable dates.
Correlate sender/recipient information with message content.

Analysis note:
The SMS database was examined as part of the mobile-device forensic workflow. Where database records were unavailable or inaccessible in Kali Linux because of Android permissions and file path, but were accessible and recovered on the Windows command terminal

Forensic significance:
SMS records can provide communication timelines and relationships between phone numbers, but their evidentiary value depends on database completeness and preservation of associated WAL/journal files.

