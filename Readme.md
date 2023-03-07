# RE&CT Ex (Extension/Experiment)

## Background:

This is an experimental project to see if I can extend or improve the ATC RE&CT Playbook & Response actions to add some functionality/useability.


With more and more Security Tools, things to monitor, and threats to protect against, the amount of potential use-cases in a SOC is growing and analysts are more likely to come to investigate an event without a solid understanding of what the detection represents.

If we consider just the Identification stage, playbooks are going to be more essential for analysts to be able to understand things like:

- What has fired, and why? 
- What could it mean, and does this event demonstrate that? (essentially False Positives/True Positives)
- What else would we expect to observe, and how might we find that?

I believe there's room for improvement on the ATC project such as incorporating some of the ideas from Mitre ATT&CK - ultimately we want analysts to be able to come to an incident without any prior knowledge or experience and not only know *what* to do, but have the context of *why* they're doing it as well as be able to contextualise the bigger picture to tell the whole story.


## Initial ideas


- To split apart Playbooks into seperate files based on stages (perhaps this could just be how the Markdown files are generated)

- For every response action, add a "Look for xyz" - based on information such as what is in Mitre ATT&CK or the original reports. Often it isn't enough to simply 
say "Find destination IPs" without the context of what should or shouldn't stand out as of interest.

- Seperating Response Actions from the 'how' such as searches, scripts etc. Instead, those searches and scripts reference the Response Action(s) that they apply to.

- Have a 1-1 Relationship between Playbooks and Mitre ATT&CK Techniques

- Use the Mitre ATT&CK Flow concept so that each Playbook has relationships between other related techniques that might have been observed before or after. The idea 
is that an event is unlikely to happen in isolation. 

- Chaining playbooks to allow a full picture of an incident can be scaled up and down based on the severity/confidence of the initial event. 
For example, a firing for a Phishing email that you discover was blocked wouldn't warrant checking the next stage which might be code execution and onwards.

