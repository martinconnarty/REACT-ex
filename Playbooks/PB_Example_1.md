# RP:Hijack Execution Flow:DLL Search Order Hijacking

## ID
- RP_1574_001

|   |   | 
|---|---|
| Author | Martin Connarty |
| Created Date | 2023/03/08 |
| Severity | M |
| TLP | AMBER |
| PAP | WHITE |

## Links
- [https://attack.mitre.org/techniques/T1574/001/](https://attack.mitre.org/techniques/T1574/001/)

## Background: (taken from Mitre ATT&CK)

Adversaries may execute their own malicious payloads by hijacking the search order used to load DLLs. Windows systems use a common method to look for required DLLs to load into a program. [1][2] Hijacking DLL loads may be for the purpose of establishing persistence as well as elevating privileges and/or evading restrictions on file execution.

There are many ways an adversary can hijack DLL loads. Adversaries may plant trojan dynamic-link library files (DLLs) in a directory that will be searched before the location of a legitimate library that will be requested by a program, causing Windows to load their malicious library when it is called for by the victim program. Adversaries may also perform DLL preloading, also called binary planting attacks, [3] by placing a malicious DLL with the same name as an ambiguously specified DLL in a location that Windows searches before the legitimate DLL. Often this location is the current working directory of the program.[4] Remote DLL preloading attacks occur when a program sets its current directory to a remote location such as a Web share before loading a DLL. [5]

Adversaries may also directly modify the search order via DLL redirection, which after being enabled (in the Registry and creation of a redirection file) may cause a program to load a different DLL.[6][7][8]

If a search order-vulnerable program is configured to run at a higher privilege level, then the adversary-controlled DLL that is loaded will also be executed at the higher level. In this case, the technique could be used for privilege escalation from user to administrator or SYSTEM or from administrator to SYSTEM, depending on the program. Programs that fall victim to path hijacking may appear to behave normally because malicious DLLs may be configured to also load the legitimate DLLs they were meant to replace.
    
## Identification:
   
When looking at this, your goal is to first verify the detection has worked accurately, then understand what is potentially being hijacked, the effect of hijacking it, and also to understand the DLL that has been loaded.

- Review the detection logic and confirm it has worked as designed [RP_2000_Understand_Detection_Logic](RP_2000_Understand_Detection_Logic)
- Try to gather details of the DLL file that was loaded 
    - [RA_20001_Gather_File_details](RA_20001_Gather_File_details)
- Understand the DLL and triage the file [RA_20002_Triage_Binary](RA_20002_Triage_Binary) and if necessary analyse it [RA_20003_Analyse_Binary](RA_20003_Analyse_Binary). 
- Look for suspicious behaviour from the hijacked executable based on what you've learned about the DLL or what you know about normal use for that executable. E.g. commands, processes or network connections you might not expect.
    - [RA_20006_Check_Child_Commands](RA_20006_Check_Child_Commands)
    - [RA_20006_Check_Child_Processes](RA_20006_Check_Child_Processes)
    - [RA_20006_Check_Process_Network](RA_20006_Check_Process_Network)

## Likely Techniques leading to this

- [PB_Example_2.md](PB_Example_2.md)

## Likely Techniques seen after this
