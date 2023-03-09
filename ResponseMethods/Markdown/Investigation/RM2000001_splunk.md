# RM2000001 - Get File Name - Splunk 

| ID | RM2000001_splunk |
|---|---|
| Author | Martin Connarty |
| Created Date | 2023/03/09 |
| Severity | M |
| TLP | AMBER |
| PAP | WHITE |

## Links

## Description

Use Splunk to gather the file name from around the time
    
## Manaul method

- If file name is unknown, look at the host in question at the time of the firing. The File name should be stored as 'FileName / File_Name'

## Scripts

- List file names based on Endpoint Indexes common information model macro

```
  `Cim_Endpoint_Indexes` | eval File_Name=coalesce(File_Name, FileName) | table _time File_Name
  ```
- List file names based on Endpoint Indexes being in the data model
```
  | tstats count from datamodel=Endpoint by ....
```
