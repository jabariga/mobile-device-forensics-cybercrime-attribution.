# Results

This folder contains the results, observations, findings, and outputs generated from the forensic analysis.



**RESULTS**



During the investigation, some artifacts that appeared unavailable or incomplete during the Linux/Kali analysis were subsequently successfully recovered when the same Android emulator was accessed through the Windows host terminal.

The results demonstrate how application databases can preserve useful forensic artifacts even when other evidence sources contain limited or no recoverable records. Findings are subject to the limitations of the acquired emulator data and the application/database versions examined.

Finding 1
Research-related email communications were successfully recovered from the Gmail application database.

Finding 2
Multiple research documents were recovered as Gmail attachments.


**Finding 3**
A project proposal was recovered from Gmail metadata.

**Finding 4**

A separate email indicates that research files were copied to an external drive and instructions were given not to upload them or share them online.

**Finding 5**
No WhatsApp artifacts relevant to the investigation were identified within the acquired dataset on Kali Linux but were recovered on Windows Command Terminal

**Finding 6**
Chrome browser artifacts contained limited evidential value relating to the investigation.

**Finding 7**
 Both SMS and call logs were recovered on Windows Command Terminal 




The investigation therefore identified a significant environment-dependent acquisition limitation.

Artifact/Operation	Kali Linux	Windows Terminal	Interpretation
ADB device access	Inconsistent at some stages	Successful		Connection/configuration difference
Application database acquisition	Some artifacts unavailable	Successfully pulled	Access path differed
WhatsApp databases	Partial/limited during some stages	Successfully acquired	Host-side ADB access was more reliable
	
Email databases	Acquisition initially problematic	Databases successfully acquired	Windows-side ADB/environment resolved
Browser evidence	Analysis performed	Evidence successfully available	Cross-platform workflow produced complementary results
Call-Logs & SMS	Partial/limited during some stages	Successfully pulled	Host-side ADB access was more reliable

SHA-256 verification	Available where file existed	Successfully performed with certutil	Local evidence path/file availability mattered




**Why did this happen?**

The difference does not necessarily mean that Linux could not analyze Android forensic artifacts. More accurately, the investigation showed that the acquisition environment affected what evidence was available to the examiner.

**Several factors contributed:**
1. ADB connection path
2. VirtualBox networking introduced an additional failure point
3. Windows had direct access to the emulator
4. File-system paths were different



**Finding: Cross-Platform Acquisition and Artifact-Recovery Limitation**

During the mobile forensic investigation, differences were observed between artifact recovery performed from the Kali Linux environment and acquisition performed directly from the Windows host.

Several artifacts that could not initially be acquired, located, or successfully processed from the Kali Linux environment were subsequently recovered successfully through the Windows terminal. This included application databases associated with WhatsApp and email, as well as other evidence acquired from the Android emulator.

The difference was primarily associated with the architecture of the laboratory environment. The Android emulator was hosted on the Windows workstation, while Kali Linux operated inside a VirtualBox virtual machine. Consequently, the Linux acquisition workflow depended on additional virtualization and network communication layers between Kali and the Android emulator. Problems involving ADB connectivity, TCP/IP communication, firewall configuration, emulator accessibility, and filesystem paths could therefore affect acquisition from Kali.

In contrast, the Windows terminal had direct access to the Android SDK, emulator and ADB installation. Once ADB connectivity was established, evidence could be acquired directly from the emulator using ‘adb pull’. The acquired files were stored in the Windows case directory and could subsequently be verified using Windows ‘certutil’.

This finding demonstrates an important forensic principle: failure to recover an artifact from one examination environment should not immediately be interpreted as evidence that the artifact does not exist on the source device. The failure may instead result from acquisition, connectivity, permissions, filesystem access, tooling, or parsing limitations.


**  Comparative Result**

** ** STAGE     **                     KALI LINUX                         WINDOWS HOST**

Emulator location    	Remote through VirtualBox/network           	Local host                                     
ADB communication    	Required additional network/VM path         	Direct host access                             
Evidence acquisition	Some artifacts initially unavailable        	Successful acquisition of additional artifacts 

Filesystem access    	Dependent on mounted/shared locations       	Native Windows filesystem   
Hash verification    	Dependent on Linux-accessible evidence copy	Direct `certutil` verification
Overall result       	Partial/inconsistent during some stages     	More complete acquisition                      

**Forensic Interpretation**

The Windows recovery of artifacts that were not initially recovered from Kali demonstrates that acquisition and analysis results can be affected by the examination environment. The investigation therefore treated the Linux failures as acquisition limitations rather than automatically classifying the corresponding artifacts as absent.

The final examination should give priority to successfully acquired and integrity-verified evidence while documenting unsuccessful acquisition attempts as limitations. Where possible, the same source artifact should be independently acquired or examined through a second trusted environment to determine whether an apparent absence is genuine or caused by an acquisition limitation.

**Research Significance**

This cross-platform difference is relevant to the research objective of evaluating mobile-device forensic acquisition. It demonstrates that a forensic workflow should not rely exclusively on a single operating system, virtualization path, acquisition tool, or ADB configuration.

The experiment supports a multi-stage validation approach in which unsuccessful acquisition is investigated before concluding that evidence is absent. A second acquisition path can reveal artifacts that were inaccessible during the initial examination and can therefore improve confidence in the completeness of the forensic examination.

