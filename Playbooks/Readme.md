# Playbooks

Playbooks are similar to those in the ATC RE&CT Project, there are a few key differences:

1. Playbooks are explicity mapped to Mitre ATT&CK Techniques

2. The generated markdown files are generated (generation script TBD) into seperate files depending on the stage, such as Preperation/Investigation etc. This is for clarity, the original YAML file contains all stages.

3. When the Markdown is generated (generation script TBD), the Response Actions will be written into the Workflow. E.g."
- "1. Look at filepath, if it is in the appdata path or the user is xyz then that may be of interest (Link to RA_xyz)..."

4. Links to any playbooks relevant to techniques that are likely to have happened either before or after the technique of interest
