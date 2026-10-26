# HTB-manager

<img src="Images/00-banner.png" width="600">

**Difficulty:** Medium

**OS:** Windows

**IP:** 10.129.116.131

**Date:** 21/10/2023

We began this machine with a port scan that revealed it was an Active Directory Domain Controller and that Certificate Services was also likely running. After discovering the website running on port 80 was likely a dead end, we switched up our approach to discovering Kerberos usernames instead. Running Kerbrute unveiled seven users. We then used crackmapexec to identify any weak userpass combinations against SMB, WinRM and MSSQL, where we had success with MSSQL with the operator Domain User.

Logging into MSSQL we performed an xp_dirtree attack which led to the discovery of a website backup file in the web root. We downloaded this file and found credentials in a hidden file which paved the way to logging into the DC as Raven using WinRM.

As Raven, we enumerated our current groups and found we were a member of Certificate Service DCOM Access. Use of Certipy revealed we had ManageCA rights. We then abused the Certificate Services to elect ourselves as an officer and created an Administrator certificate where we authenticated and retrieved an NT hash before logging into the Domain Controller using Impacket and obtaining SYSTEM access.

**Key Findings**


| Finding         | Severity     | Impact                                                         |
| :-------------- | :----------- | :------------------------------------------------------------- |
| Weak Credentials | High:&nbsp;8.1 | Weak credentials leading to unauthorised MSSQL access. |
| Exposed password | High:&nbsp;8.1 | Unencrypted plaintext password stored in website backup file. |
| ESC7&nbsp;Misconfiguration | Critical:&nbsp;9.8 | Misconfiguration allows elevation of privilege from normal to administrator user. |


