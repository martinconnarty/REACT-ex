# Response Actions

Response actions in principal are the same as the ATC RE&CT Project, although there are a few key differences:


1. There is another level below Response Actions, a 'how' layer called Response Methods. This means if in our playbook it says "do XYZ", we may have a inline script for this, 
or a manual method, or more. Each might depend on the technology or tools we have available. Response Actions essentially act as the signpost to these.

2. The (TBD) plan is that Markdown for Response Actions is generated dynamically based on the technology options you have available. If for example you have Splunk and Sysmon, then 
the methods for 'find the File Hash' will list links to Response Methods for doing it in Splunk. If you don't, then they won't show up.
