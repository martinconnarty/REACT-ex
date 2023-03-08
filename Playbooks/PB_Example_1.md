# RP:Hijack Execution Flow:DLL Search Order Hijacking

## RP_1574_001

## Tags
- T1574

## author
- Martin Connarty
## creation_date
- 2023/03/08

## Severity
- M 

## tlp
- AMBER 

## pap
- WHITE  

## Links
- (https://attack.mitre.org/techniques/T1574/001/)[https://attack.mitre.org/techniques/T1574/001/]

## Background: (taken from Mitre ATT&CK) This technique is used to cause a legitimate binary to execute malicious code. 

Adversaries may execute their own malicious payloads by hijacking the search order used to load DLLs. Windows systems use a common method to look for required DLLs to load into a program. [1][2] Hijacking DLL loads may be for the purpose of establishing persistence as well as elevating privileges and/or evading restrictions on file execution.

There are many ways an adversary can hijack DLL loads. Adversaries may plant trojan dynamic-link library files (DLLs) in a directory that will be searched before the location of a legitimate library that will be requested by a program, causing Windows to load their malicious library when it is called for by the victim program. Adversaries may also perform DLL preloading, also called binary planting attacks, [3] by placing a malicious DLL with the same name as an ambiguously specified DLL in a location that Windows searches before the legitimate DLL. Often this location is the current working directory of the program.[4] Remote DLL preloading attacks occur when a program sets its current directory to a remote location such as a Web share before loading a DLL. [5]

Adversaries may also directly modify the search order via DLL redirection, which after being enabled (in the Registry and creation of a redirection file) may cause a program to load a different DLL.[6][7][8]

If a search order-vulnerable program is configured to run at a higher privilege level, then the adversary-controlled DLL that is loaded will also be executed at the higher level. In this case, the technique could be used for privilege escalation from user to administrator or SYSTEM or from administrator to SYSTEM, depending on the program. Programs that fall victim to path hijacking may appear to behave normally because malicious DLLs may be configured to also load the legitimate DLLs they were meant to replace.
    
## Identification:
   
- When looking at this, your goal is to verify this has occured, understand what is potentially being hijacked and is it even vulnerable to DLL Search Order hijacking? (RA_80004_Testing_DLL_Hijacking) , and then to identify the DLL file that was loaded (RA_20001_Identify_File), understand it and triage it (RA_20002_Triage_Binary) and if necessary analyse it (RA_20003_Analyse_Binary). 
- Can you identify how the DLL was initially placed there? Look at the identification steps on RP_1059_Command_and_Scripting or RP_1024_User_Execution
- Can you identify whether or not it succeeded? If you have done some analysis on the binary you may have network indicators, or you may be able to look for unusual behaviour for the targetted Exe. (RA_20004_Check_Network_Logs)
    
## Likely Techniques leading to this

- (PB_Example_2.md)[PB_Example_2.md]

## Likely Techniques seen after this
