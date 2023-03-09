# RE&CT Ex (Extension/Experiment)

## Background:

This is an experimental project to see if I can extend or improve the [ATC RE&CT](https://github.com/atc-project/atc-react) Playbook & Response actions to add some functionality/useability. 

With more and more Security Tools, things to monitor, and threats to protect against, the amount of potential use-cases in a SOC is growing and analysts are more likely to come to investigate an event without a solid understanding of what the detection represents.

If we consider just the Identification stage, playbooks are going to be more essential for analysts to be able to understand things like:

- What has fired, and why? 
- What could it mean, and does this event demonstrate that? (essentially False Positives/True Positives)
- What else would we expect to observe, and how might we find that?

I believe there's room for improvement on the ATC project such as incorporating some of the ideas from Mitre ATT&CK and improving the useability. I think logically everything in RE&CT makes a lot of sense, but (and this is probably a me problem), I find the playbooks a bit unweildy/hard to use. 

Ultimately we want analysts to be able to come to an incident without any prior knowledge or experience and not only know *what* to do, but have the context of *why* they're doing it as well as be able to contextualise the bigger picture to tell the whole story.

##  Changelog

- 2022-Mar-09 Worked on some Response Action and Method markdown and YAML files
- 2022-Mar-08 https://github.com/martinconnarty/REACT-ex/blob/main/Playbooks/PB_Example_1.md - Working on designing a simple to use playbook layout


## Initial ideas/thoughts


- To split apart or make it easy to split Playbooks into seperate files based on stages (perhaps this could just be how the Markdown files are generated). Because Playbooks currently comprise of all the full stages, it can quickly become unweildy with many different Response actions and becomes hard to follow.

- For every response action, add some context of how to use it, e.g. "Look for xyz". This could be based on information such as what is in Mitre ATT&CK or the original reports. Often it isn't enough to simply say "Find destination IPs" without the context of what should or shouldn't stand out as of interest for that use-case. I appreciate that at the moment there is a Markdown 'Workflow' section that could satisfy that if used well. They key point is having the context alongside the actions.

- Seperating Response Actions from the 'how' such as searches, scripts etc. Instead, those searches and scripts reference the Response Action(s) that they apply to.

- Have a 1-1 Relationship between Playbooks and Mitre ATT&CK Techniques. At the moment it doesn't seem clear what drives the requirement for playbooks but also by their being too high level we can end up with Response Actions which don't apply to what is being looked at.

- Use the Mitre ATT&CK Flow concept so that each Playbook has relationships between other related techniques that might have been observed before or after. The idea is that an event is unlikely to happen in isolation and should be seen as part of a chain that needs understanding. 

- Chaining playbooks to allow a full picture of an incident which can be scaled up and down based on the severity/confidence of the initial event. 
For example, a firing for a Phishing email that you discover was blocked wouldn't warrant checking the next stage which might be code execution and onwards, or you might not have a high degree of confidence that it is a true positive, by looking at what would likely happen after or have happened before, you may be able to support a conclusion of false positive or identify further events.


![image](Attack%20flow.png)

