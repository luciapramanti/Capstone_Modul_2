# Improving Transjakarta Service : an Exploratory Data Analysis
This project delves into the data analytics of Transjakarta's operations, exploring patterns in ridership, passenger profiles, and areas for potential improvement. By leveraging data insights, the aim is to enhance the efficiency and effectiveness of this critical public service.

### Business Problem
PT Transjakarta's objective is to offer a safe and comfortable journey for all its users. To improve the service, PT Transjakarta is seeking to identify any specific patterns in its user data that could be leveraged as insights for futher improvements and developments.

### Business Questions
Patterns of the journeys.
* What is the average journey duration of Transjakarta users?
* When does the level of usage increase and by how much?

Corridor-specific patterns
* Which corridors are the busiest?
* Is the corridor bus capacity adequate?
* What can be done to improve the service?

Bus stop-specific patterns
* Which bus stops are the busiest?
* How to improve services at bus stops?

Information regarding the characteristic patterns of the users:
* By gender: What is the ratio of female to male users?
* By age: What is the age of the majority of users? Are there elderly users?
* What can be done to improve the journey for the elderly?

**Key Questions**:  How can we optimize the performance of Transjakarta's fleet, facilities, and operational aspects? 

### Dataset
1. transID : Unique transaction id for every transaction
2. payCardID : Customers main identifier. The card customers use as a ticket for entrance and exit.
3. payCardBank : Customers card bank issuer name
4. payCardName : Customers name that is embedded in the card.
5. payCardSex : Customers sex that is embedded in the card
6. payCardBirthDate : Customers birth year
7. corridorID : Corridor ID / Route ID as key for route grouping.
8. corridorName : Corridor Name / Route Name contains Start and Finish for each route.
9. direction : 0 for Go, 1 for Back. Direction of the route.
10. tapInStops : Tap In (entrance) Stops ID for identifying stops name
11. tapInStopsName : Tap In (entrance) Stops Name where customers tap in.
12. tapInStopsLat : Latitude of Tap In Stops
13. tapInStopsLon : Longitude of Tap In Stops
14. stopStartSeq : Sequence of the stops, 1st stop, 2nd stops etc. Related to direction.
15. tapInTime : Time of tap in. Date and time
16. tapOutStops : Tap Out (Exit) Stops ID for identifying stops name
17. tapOutStopsName : Tap out (exit) Stops Name where customers tap out.
18. tapOutStopsLat : Latitude of Tap Out Stops
19. tapOutStopsLon : Longitude of Tap Out Stops
20. stopEndSeq : Sequence of the stops, 1st stop, 2nd stops etc.Related to direction.
21. tapOutTime : Time of tap out. Date and time
22. payAmount : The number of what customers pay. Some are free. Some not. are free. Some not.

### Analysis Framework
* Trip Duration
* Trip Frequency
* Ridership Pattern : Corridor
    * Busiest corridors during peak hours 
* Ridership Pattern : Tap-in and Tap-out Stops
    * Busiest bus stop during peak hours
* Demographic : Gender
* Inclusivity : Service for elderly

For more visualization please visit this link:  https://public.tableau.com/app/profile/lucia.pramanti/viz/CapstoneModul2-Lucia/Dashboard1

Presentation file can be found at this link : https://www.canva.com/design/DAGKe7WozgA/cFaATmsgfxrtT660c9DAGg/view?utm_content=DAGKe7WozgA&utm_campaign=designshare&utm_medium=link&utm_source=editor
