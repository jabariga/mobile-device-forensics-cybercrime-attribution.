# Reports

This folder contains forensic analysis reports, findings, summaries, and supporting documentation produced during the project.




REPORTS

**Forensic Findings**

Finding 1 — Browser activity

Browser databases contained multiple search terms and visited URLs. Several searches were security/privacy related.

Assessment: Relevant digital activity identified; intent cannot be established solely from searches.

Finding 2 — WhatsApp communications

WhatsApp database analysis recovered timestamped sent and received messages.

Examples included communications concerning employment, account information and organizational matters.

Assessment: Communication artifacts were successfully recovered and chronologically reconstructed.

Finding 3 — Email database
Messages and attachments were recovered from the examined EmailProvider.db.

Assessment: Negative finding; absence from this database does not establish that no email activity occurred.

Finding 4 — WhatsApp call records
The examined call log table contained no records.

Assessment: No call records were identified in the examined database on Kali Linux 

Finding 5 — Evidence integrity

SHA-256 hashing was performed on acquired artifacts including wa.db and browser evidence.

Assessment: Hashing provides a mechanism for verifying that the examined evidence copy has not changed after acquisition.

**Executive Summary**

This investigation examined selected artifacts from an Android-based mobile forensic environment with the objective of demonstrating the acquisition and analysis of browser, email, SMS, WhatsApp, and call-related evidence. Application databases were acquired using ADB and examined using SQLite. SHA-256 hashing was used to support evidence-integrity verification.
Browser examination identified search activity relating to CCTV retention, PDF metadata, secure file deletion, GPS metadata, VPNs and other subjects. WhatsApp examination recovered timestamped message conversations and participant identifiers. The examined Email Provider database contained no recoverable message or attachment records, while the examined WhatsApp call-log table contained no call records.


** Limitations**

** 1. Cross-platform acquisition limitations**
Some artifacts were not initially recovered or were inaccessible when acquisition was performed from Kali Linux. The same Android emulator was later successfully accessed through the Windows host, where additional artifacts were recovered. This indicates that failure to recover an artifact from one environment does not necessarily mean that the artifact was absent from the device.
** 2. Virtualization and network dependency**
Kali Linux was operated inside VirtualBox while the Android emulator was running on the Windows host. This introduced additional networking and virtualization layers that affected ADB communication and evidence acquisition.
** 3. ADB connectivity limitations**
The investigation experienced periods where ADB devices were unavailable, offline, or inaccessible. Consequently, acquisition depended on establishing a stable ADB connection before evidence could be collected.
 **4. Android permissions and access restrictions**
Some application directories and databases could not be accessed from non-rooted Android environments. For example, direct access to protected application data may produce permission errors even though the application itself is functioning normally.
** 5. Application/database version differences**
WhatsApp and email databases did not necessarily contain the same schema, tables, or artifacts expected from older forensic examples. Database structures therefore had to be examined using commands such as PRAGMA table_info() and .schema before queries could be constructed.
** 6. Incomplete or empty artifacts**
Some databases were successfully acquired but contained no records of interest. For example, the email Message and Attachment tables returned zero records, while EmailProviderBody.db contained an empty Body table. This limited the amount of email evidence available for analysis.
** 7. Media and auxiliary artifact limitations**
Although WhatsApp media was successfully pulled from the emulator, individual-file hashing required identification of the actual files rather than using placeholder paths. Therefore, acquisition and verification had to be performed in separate stages.
** 8. Synthetic/laboratory environment**
The investigation was performed using an Android emulator and controlled forensic test data rather than a real seized device from an active criminal investigation. Therefore, the findings demonstrate forensic techniques and workflow rather than establishing conclusions about an actual criminal case.
** 9. Data sanitization and publication constraints**
Evidence intended for GitHub publication must be sanitized to prevent disclosure of personal information, authentication credentials, tokens, private messages, phone numbers, and other sensitive information. Consequently, the public repository cannot contain an unrestricted copy of the original forensic evidence.
** 10. Tool and environment dependencies **
Results may vary depending on Android version, application version, ADB version, operating system, emulator configuration, database schema, permissions, and forensic tools. The results obtained in this laboratory should therefore not be assumed to apply identically to every Android device.

**SUMMARY**
The investigation demonstrated that mobile forensic artifact recovery can be environment-dependent. Artifacts that were initially unavailable through the Kali Linux forensic environment were subsequently recovered through direct Windows-host acquisition. This indicates that an unsuccessful acquisition from one examination environment should not automatically be interpreted as evidence of absence. Cross-platform validation may therefore be necessary to distinguish genuine artifact absence from acquisition, connectivity, permission, or tooling limitations.


