# Kata2023_team_onion

This is a github space for the Architectural Katas Challenge Fall 2023 - Team Onion Elimination Round submission

![team onion](https://www.thespruce.com/thmb/ROmJ5HxENbIu7-v6-3WjUHVR7wU=/750x0/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/growing-onions-1403447-01-38d480a2d16d4ea0b0dd174f42785e1d.jpg)

Team Members:  
[Bas Bartelink](https://www.linkedin.com/in/basbartelink/)  
[Mart Brouwer](https://www.linkedin.com/in/mart-brouwer/)  
[Kees van Dolderen](https://www.linkedin.com/in/kees-van-dolderen/)  
[Guilbert Payusan](https://www.linkedin.com/in/guilbert-magtuto-payusan-914a3985/)  
[Karol Skrzymowski](https://www.linkedin.com/in/karolskrzymowski/)  

## Contents

1. [Glossary](#glossary)  
2. [Problem Background](#problem-background)  
    - [Introduction](#introduction)  
    - [Requirements](#requirements)  
    - [Additional Context](#additional-context)  
3. [Constraints and Assumptions](#constraints-and-assumptions)  
    - [Technical Constraints](#technical-constraints)  
    - [Assumptions](#assumptions)  
4. [Architectural Characteristics](#architectural-characteristics)  
    - [Driving Characteristics](#driving-characteristics)  
    - [Implicit Characteristics](#implicit-characteristics)  
    - [Other Considered](#other-considered)  
5. []()  
6. []()  
7. []()  
8. []()  
9. []()  
    - []()  
    - []()  
10. []()  

## 1. Glossary

|Term             |Definition                                                                                |
|-----------------|------------------------------------------------------------------------------------------|
| | |
| | |
| | |

## 2. Problem Background
### Introduction
The Problem: The Road Warrior  
A new startup wants to build the next generation online trip management dashboard to allow travelers to see all of their existing reservations. Organized by trip either online (web) or through their mobile device.  
### Requirements
- Poll email looking for travel-related emails,  
- Filter and whitelist certain emails,  
- The system must interface with the agency’s existing airline, hotel, and car rental interface system to update travel details (delays, cancellations, updates, gate changes, etc.). Updates must be in the app within 5 minutes of an update (better than the competition),  
- Customers should be able to add, update, or delete existing reservations manually as well,  
- Items in the dashboard should be able to be grouped by trip, and once the trip is complete, the items should automatically be removed from the dashboard,  
- Users should also be able to share their trip information by interfacing with standard social media sites or allowing targeted people to view your trip,  
- Richest user interface possible across all deployment platforms,  
- Provide end-of-year summary reports for users with a wide range of metrics about their travel usage,  
- Road Warrior gathers analytical data from users trips for various purposes - travel trends, locations, airline and hotel vendor preferences, cancellation and update frequency, and so on,  
### Additional Context
- Must integrate seamlessly with existing travel systems (i.e, SABRE, APOLLO),  
- Must integrate with preferred travel agency for quick problem resolution (help me!) must work internationally technical requirements,  
- Users must be able to access the system at all times (max 5 minutes per month of unplanned downtime),  
- Travel updates must be presented in the app within 5 minutes of generation by the source,  
- Response time from web (800ms) and mobile,  

Users  
- 2 million active users/week, 
- total users: 15 million (user accounts)  

## Constraints and Assumptions

### Assumptions
|ID|Name|Description|
|-|-|-|
|1.|Profit goal|Road Warrior service is provided for free, income generated by selling the analytical data from user trips.|
|2.|Travel Agancy|Road Warrior service is not a travel agency system, but an aggregator of user travel data from multiple sources. Because of that no reservations can be made over the Road Warrior UI or API.|
|3.|Standardized interfaces|Data sources have standardized APIs where travel systems cover a majority of service providers in different categories, but along that major service chains (like SIXT for car rental or Marriott for hotels) may have their own APIs.|
|4.|Webhooks|Standardized APIs of data sources are capable of providing webhooks methods for subscribing to asynchronous data feeds.|
|5.|Data from sources|A single source (travel agencies, travel systems, airlines, etc.) always provides new information and do not duplicate its own updates.|

## Architectural Characteristics

### Driving Characteristics
|Name|Core|Definition|Rationale|
|-|-|-|-|
|Security||This refers to the protection of software, data, and systems against unauthorized access, use, disclosure, disruption, modification, or destruction. It involves various measures and techniques to guard against cyber threats and vulnerabilities.||
|Interoperability|X|It is the ability of different software systems, devices, or applications to connect, communicate, and work together without any special effort. For software, this means being able to exchange and make use of information seamlessly with other software or systems.||
|Auditability||This is the capability of a system to provide a traceable record of all actions and transactions. It allows organizations to review and verify the accuracy and authenticity of operations and data, often used for regulatory compliance and for identifying potential security breaches.||
|Performance|X|It encompasses the speed, responsiveness, and efficiency of a system. Performance can be gauged by factors like load times, throughput (rate of processing), and latency (time delay). High-performance software ensures tasks are completed without unnecessary delays.||
|Usability|X|Refers to how user-friendly a software or system is. It's about designing products that are easy to use, efficient, and satisfying. Usability takes into account the user experience, which includes the design, interface, and overall interaction with the software.||
|Portability||This is the ease with which software can be transferred from one computing environment to another. A portable software can run on different types of hardware, operating systems, or configurations without requiring significant changes.||
|Privacy||Concerns the protection of user data and information. Software designed with privacy in mind ensures that user data is collected, stored, and processed in a manner that respects and safeguards the user's rights. This includes aspects like data encryption, anonymization, and compliance with privacy regulations.|Legal and regulatory compliance: As many countries and regions, where Road Warrior will be available, have enacted strict data protection laws and regulations, such as the European Union's General Data Protection Regulation (GDPR) and the California Consumer Privacy Act (CCPA). We need to ensure compliance with such legal requirements, avoiding potential legal and financial consequences. User rights: To warrant individuals' privacy rights, such as the right to access, correct, or delete their personal data. We need to ensure that Road Warrior has processes and/or functionality in place to handle such requests efficiently and in compliance with legal requirements. Enhancing user consent and transparency: Road Warrior needs to include mechanisms for obtaining and managing user consent for data processing activities. This also promotes transparency by providing clear and accessible privacy policies and notices, informing users about how their data is collected, used and shared.|

### Implicit Characteristics

|Name|Definition|Rationale|
|-|-|-|
|Feasibility|This refers to the practicality of implementing a particular solution or feature in software development. It considers various factors including technical constraints, available resources, time, and financial implications. When assessing feasibility, the question is: "Can this be done given our current circumstances?"||
|Legal|This relates to ensuring that the software adheres to all legal requirements and standards. This could range from licensing considerations to data protection regulations and other relevant laws. It's crucial to ensure software doesn't inadvertently violate any legal mandates.|Legal and regulatory compliance: As many countries and regions, where Road Warrior will be available, have enacted strict data protection laws and regulations, such as the European Union's General Data Protection Regulation (GDPR) and the California Consumer Privacy Act (CCPA). We need to ensure compliance with such legal requirements, avoiding potential legal and financial consequences. User rights: To warrant individuals' privacy rights, such as the right to access, correct, or delete their personal data. We need to ensure that Road Warrior has processes and/or functionality in place to handle such requests efficiently and in compliance with legal requirements. Enhancing user consent and transparency: Road Warrior needs to include mechanisms for obtaining and managing user consent for data processing activities. This also promotes transparency by providing clear and accessible privacy policies and notices, informing users about how their data is collected, used and shared.|
|Maintainability|This is about how easily software can be modified to correct faults, improve performance, or adapt to a changing environment. A maintainable system is structured in a way that makes updates and fixes straightforward without causing disruptions or introducing new issues.||
|Simplicity|This characteristic is grounded in the principle that software should be as simple as necessary (but no simpler). Overcomplicating a system can lead to various issues down the line. Software that embraces simplicity tends to be more understandable, easier to maintain, and less prone to errors. It's often guided by the KISS principle: "Keep It Simple, Stupid."||

### Other Considered

|Name|Definition|Rationale|
|-|-|-|
|Learnability|This pertains to how easily new users can begin effective interaction and achieve maximum performance with a software application or system. In essence, it's about the ease with which users can understand and get accustomed to the features and functionalities of a software product. High learnability ensures that users can quickly become proficient with the software, reducing the need for extensive training or support.||
|Accessibility|Accessibility focuses on designing software that can be used by all people, regardless of their abilities or disabilities. This means creating software that is usable by people with a wide range of physical and cognitive abilities. Accessibility considerations often include features like screen reader compatibility for the visually impaired, alternative input methods for those with motor disabilities, and clear, understandable content presentation for those with cognitive impairments. Adhering to accessibility standards not only widens the user base but also fulfills legal and ethical responsibilities in many jurisdictions.||

