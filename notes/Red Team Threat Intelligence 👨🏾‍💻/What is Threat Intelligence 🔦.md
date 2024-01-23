**Threat Intelligence (TI)** or **Cyber Threat Intelligence (CTI)** is the information, or TTPs (**T**actics, **T**echniques, and **P**rocedures), attributed to an adversary, commonly used by defenders to aid in detection measures. The red cell can leverage CTI from an offensive perspective to assist in adversary emulation.

CTI can be consumed (to taken action upon data) by collecting IOCs (**I**ndicators **o**f **C**ompromise) and TTPs commonly distributed and maintained by [ISACs (**I**nformation and **S**haring **A**nalysis **C**enters)](https://tryhackme.com/room/introtoisac). Intelligence platforms and frameworks also aid in the consumption of CTI, primarily focusing on an overarching timeline of all activities.

_Note: The term ISAC is used loosely in the threat intelligence landscape and often refers to a threat intelligence platform._

Traditionally, defenders use threat intelligence to provide context to the ever-changing threat landscape and quantify findings. IOCs are quantified by traces left by adversaries such as domains, IPs, files, strings, etc. The blue team can utilize various IOCs to build detections and analyze behavior. From a red team perspective, you can think of threat intelligence as the red team's analysis of the blue team's ability to properly leverage CTI for detections.

![|200](./img/Pasted%20image%2020240123220800.png)