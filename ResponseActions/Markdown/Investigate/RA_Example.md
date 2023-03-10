# RA: Get File Details

| ID | RA20001 |
|---|---|
| Author | Martin Connarty |
| Created Date | 2023/03/09 |
| Severity | M |
| TLP | AMBER |
| PAP | WHITE |

## Links

## Description

Get some basic details about a file, such as where it ran from, its name, file hash etc.
    
## Identification:
1. Get the file name and file path and (if logs support, the file hash)
      - [RM2000001_Splunk](../../../Response_Methods/Investigate/RM2000001_Splunk)
2. (Optional) Generate the file hash if access the the box is safe/not going to ruin forensics:
      - [RM2000002_Windows](../../../Response_Methods/Investigate/RM2000002_Windows)
3. Check if the file is signed and who by
      - [RM2000003_Windows](../../../Response_Methods/Investigate/RM2000003_Windows)
4. Check the file created, modified, and accessed dates 
      - [RM2000004_Windows](../../../Response_Methods/Investigate/RM2000004_Windows)
