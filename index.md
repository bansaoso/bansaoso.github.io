---
layout: default
title: Home
---
<h1><strong>Digital Forensics</strong></h1>

***

## Course Implementation Plan

- Module 1: Introduction

- Module 2: Key Technical Concepts

- Module 3: Labs and Tools

- Module 4: Collecting Evidence

- Module 5: Windows System Artifacts

- Module 6: Antiforensics

- Module 7: Legal

- Module 8: Internet and E-Mail

- Module 9: Digital Forensics and Networking

- Module 10: Mobile Device Forensics

---

## Labs

- Lab 1: Introduction to Digital Forensics software
- Lab 2: Data Carving
- Lab 3: USB Image Acquisition
- Lab 4: Disk Image and Partitions
- Lab 5: Examining the Registry
- Lab 6: Update Sequence Number (USN) Journaling
- Lab 7: Recycle Bin and Anti-forensics
- Lab 8: Bypassing a BIOS Password
- Lab 9: Password Cracking of Windows Operating System
- Lab 10: File search based on metadata
- Lab 11: Investigating browser history
- Lab 12: Email forensics
- Lab 13: The Sleuth Kit
- Lab 14: Mobile App Investigations Messaging

### [Lab 5] Registry Forensics with RegRipper plug-ins
- Here’s a list of the registry hives present in almost all Windows systems:
  - `HKEY_CURRENT_CONFIG`: supported by the `System`, `System.alt`, `System.log`, and `System.sav` files
  - `HKEY_CURRENT_USER`: supported by the `Ntuser.dat` and `Ntuser.dat.log` files
  - `HKEY_LOCAL_MACHINE\SAM`: supported by the `Sam`, `Sam.log`, and `Sam.sav` files
  - `HKEY_LOCAL_MACHINE\Security`: supported by the `Security`, `Security.log`, and `Security.sav` files
  - `HKEY_LOCAL_MACHINE\Software`: supported by the `Software`, `Software.log`, and `Software.sav` files
  - `HKEY_LOCAL_MACHINE\System`: supported by the `System`, `System.alt`, `System.log`, and `System.sav` files
  - `HKEY_USERS\.DEFAULT`: supported by the `Default`, `Default.log`, and `Default.sav` files
- In digital forensics, these registry hives can tell investigators:
  - `HKEY_CURRENT_CONFIG`: acts as a pointer or shortcut to a registry key containing information about the computer's hardware profile
  - `HKEY_CURRENT_USER`: contains the computer settings the current user prefers (e.g., what software he/she typically uses)
  - `HKEY_LOCAL_MACHINE\SAM`: contains local user account and local group membership information, including passwords. It also tells you what privileges are granted (e.g., what files they can access) to each user and group in the Active Directory
  - `HKEY_LOCAL_MACHINE\Security`: contains local system security policy settings that control which domains are trusted to authenticate login attempts, which users are allowed to access the system, on what channels users are permitted to access the system, which privileges are assigned to a user, how users are audited, and login information for cached domain and service logins
  - `HKEY_LOCAL_MACHINE\Software`: contains most of the configuration information for the software installed on the computer and the OS
  - `HKEY_LOCAL_MACHINE\System`: contains the same information as HKEY_LOCAL_MACHINE\Software
  - `HKEY_USERS\.DEFAULT`: contains the registry settings used as the default for the currently logged-in user. If that user doesn’t have an existing profile, the C:\Users\Default\ntuser registry hive will get called
- Windows Registry Forensics
  - Determining installed product information: `perl rip.pl -r software -p product`
  - Determining the product type: `perl rip.pl -r system -p producttype`
  - Determining the Windows version: `perl rip.pl -r software -p winver`
  - Determining the network cards used: `perl rip.pl -r software -p networkcards`
  - Determining the DHCP information: `perl rip.pl -r system -p nic`
  - Determining the wireless access points information: `perl rip.pl -r software -p ssid`
  - Determining the shutdown time: `perl rip.pl -r system -p shutdown`
  - Determining the time zone: `perl rip.pl -r system -p timezone`
  - Determining all installed applications: `perl rip.pl -r software -p uninstall`
  - Determining user SIDs: `perl rip.pl -r software -p profilelist`
  - Determining the recent documents used: `perl rip.pl -r NTUSER.DAT -p recentdocs`
  - Extracting information from the `winlogon` key: `perl rip.pl -r software -p winlogon`
  - Determining suspect's web-browsing history: `perl rip.pl -r NTUSER.DAT -p typedurls`
  - Collecting information about unread emails: `perl rip.pl -r NTUSER.DAT -p unreadmail`
  - Determining applications set to auto start: `perl rip.pl -r NTUSER.DAT -p user_run`
  - Determining the value of the `userinit` registry key: `perl rip.pl -r software -p userinit`
  - Determining the user's printers: `perl rip.pl -r NTUSER.DAT -p printers`
  - Collecting information about `Cain & Able`: `perl rip.pl -r NTUSER.DAT -p cain`

---

## Quiz

### Key Technical Concepts

CCSF's Web4 lets students enroll in classes online. What type of cloud computing is it? 
- *SaaS*  
- PaaS  
- IaaS  
- None of the above  

A company moves to the cloud, taking images of their servers, routers, and switches, and deploying them to Amazon's servers as virtual machines and software-defined networks. What type of cloud service is that?  
- SaaS  
- PaaS  
- *IaaS*  
- None of the above  

Tyler makes a Word document and saves it on his desktop. What type of data is it?
- *Active data*  
- Latent data  
- Archival data  
- Metadata  
- None of the above  

Tyler deletes the document, so it goes into the Recycle Bin. What type of data is it?
- Active data  
- *Latent data*  
- Archival data  
- Metadata  
- None of the above  

Tyler empties his Recycle Bin, so the Word document is gone. What type of data is it?
- Active data  
- *Latent data*  
- Archival data  
- Metadata  
- None of the above  

Tyler uses DISKPART and CLEAN ALL to write zeroes to his whole hard drive, including the Word document. What type of data is the Word document now?
- Active data  
- Latent data  
- Archival data  
- Metadata  
- *None of the above*  

### Labs and Tools

Which of these documents is most important, and can ruin the evidence if it is lost?
- *Chain of custody*  
- Examiner's final report  
- Summary  
- Detailed findings  
- Glossary  

Which of these items must be written in clear, non-technical English?
- Chain of custody  
- *Examiner's final report*  
- Summary  
- Detailed findings  
- Glossary  

Which is the most reliable forensic software?
- FTK  
- EnCase  
- SleuthKit and Autopsy  
- ProDiscover  
- *Never trust any of them, always use two*  

### Collecting Evidence

Which item must be placed in a Faraday bag immediately after seizure?
- SD cards  
- Thumb drive  
- Hard disk  
- *Cell phone*  
- Laptop  

Which item of evidence is the most volatile?
- Deleted files on a hard disk  
- *Downloads in progress*  
- Archival data  
- Data stored in the cloud  
- USB thumbdrive data  

If a suspect is using encryption, which data below is likely to be lost if the device is powered off? 
- Cell phone  
- USB thumb drive  
- *Contents of RAM*  
- Laptop hard drive  
- All of the above  

Which is the first step done by a forensic examiner who arrives at a crime scene?
- Take photographs  
- Label devices  
- *Take notes*  
- Fill out Chain of Custody form  
- Remove extra people  

Joe is making a clone of the evidence drive onto a target drive. Which of these is NOT a good practice?
- Forensically wipe target drive first  
- Use antivirus to scan the forensic workstation  
- *Use antivirus to scan the evidence drive*  
- Use a hardware write-blocker  
- Calculate the MD5 hash  

You find a laptop at a crime scene with a dead battery. What type of acquisition should you perform?
- Live acquisition in a laboratory  
- *Static acquisition in a laboratory*  
- Live acquisition at the scene  
- Static acquisition at the scene  
- They are all equally useful  

You find a cell phone at a crime scene with a low battery, and no charger is available. What type of acquisition should you perform?
- Live acquisition in a laboratory  
- Static acquisition in a laboratory  
- *Live acquisition at the scene*  
- Static acquisition at the scene  
- They are all equally useful  

### Windows System Artifacts

Which type of data is created when a laptop lid is closed?
- Deleted data  
- *Hiberfil*  
- Page file  
- Registry  
- Metadata  

Which type of data must be reconstructed with file carving?
- Thumbnails  
- MRU list  
- Restore points  
- *Deleted data*  
- Metadata  

Where is the identity of the last-logged-in user stored?
- MRU list  
- Hiberfil  
- Page file  
- *Registry*  
- Metadata  

Where is the Modified timestamp for a file stored?
- MRU list  
- Hiberfil  
- Page file  
- Registry  
- *Metadata*  

### Anti-forensics

What term best describes BASE64 encoding?
- Encryption  
- *Obfuscation*  
- Steganography  
- Hashing  
- Destruction  

Which method uses one key to encrypt, and a different key to decrypt?
- Symmetric encryption  
- *Asymmetric encryption*  
- Hashing  
- More than one of the above  
- None of the above  

Which of these is a hardware device?
- BitLocker  
- FileVault  
- TrueCrypt  
- *TPM*  
- EFS  

If you see a repeated pattern of DEADBEEF for a large portion of a hard drive, what does this indicate?
- BitLocker  
- FileVault  
- TrueCrypt  
- *Drive wiping*  
- Obfuscation  

### Legal

Which law protects you from third-party wiretaps?
- Fourth amendment  
- First amendment  
- *ECPA*  
- SCA  
- ESI  

Boston police searched houses for the bomber without warrants. What justification did they have for that?
- Probable cause  
- Consent  
- *Exigent circumstances*  
- Reasonable expectation of privacy  
- Eminent domain  

What starts as soon as there is a reasonable expectation of litigation?
- eDiscovery  
- Spoilation  
- *Duty to preserve*  
- ESI  
- Data sampling  

### Internet and Email

What is the technical term for the last part of a Web address, such as .com or .net?
- HTTP  
- *TLD*  
- IP  
- DNS  
- HTML  

Which item is deceptive, often containing data from a Web site the suspect never visited?
- P2P  
- Index.dat  
- *Cookie*  
- Web cache  
- MSHist files  

Which protocol is used to send email?
- DNS  
- TCP  
- *SMTP*  
- IMAP  
- POP  

### Digital Forensics and Networking

What type of network is the Internet?
- *WAN*  
- PAN  
- MAN  
- CAN  
- LAN  

What type of attack could be prevented by egress filtering?
- DDoS  
- *IP Spoofing*  
- MITM  
- Social engineering  
- Insider  

What part of the Incident Response process involves finding out how large the problem is and making sure it stops growing?
- Detection and analysis  
- *Containment*  
- Eradication  
- Recovery  
- Post-incident review  

### Mobile Device Forensics

Which phones use an ESN to identify them?
- PSTN  
- *CDMA*  
- GSM  
- iDEN  
- GPS  

Which phones use SIM cards?
- PSTN  
- CDMA  
- *GSM*  
- iDEN  
- GPS  

What is the most popular phone OS?
- Windows Phone  
- *Android*  
- iOS  
- Symbian  
- Unix  

Which devices store a track log of physical locations automatically?
- CDMA  
- GSM  
- iDEN  
- *GPS*  
- Prepaid  

### Looking Ahead – Challenges and Concerns

Which term describes long-term off-site storage of old data?
- Data remanence  
- *Cloud persistence*  
- Previous versions  
- Time Machine  
- BitLocker  

Which term describes data accidentally left on discarded devices?
- *Data remanence*  
- Cloud persistence  
- Previous versions  
- Time Machine  
- BitLocker  

What activity of an SSD controller causes write operations to one block to actually store data on some other block?
- Cloud persistence  
- Defragmentation  
- *File translation layer*  
- Garbage collection  
- IaaS  

What activity of an SSD controller causes latent data to vanish?
- Cloud persistence  
- Defragmentation  
- File translation layer  
- *Garbage collection*  
- IaaS  

---

## Learning Materials
- John Sammons. _The Basics of Digital Forensics: The Primer for Getting Started in Digital Forensics_, 2nd Edition, December 29, 2014, Syngress.
- [Introduction to Cyber Security)](/_data/Introduction-cyber-security.pdf)
- [An Introduction to Information Security (NIST)](/_data/NIST.SP.800-12r1.pdf)
