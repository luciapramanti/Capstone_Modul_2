{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "69ea6af4-2fa8-42c9-9bf3-4223d3b15e62",
   "metadata": {},
   "source": [
    "# Improving Transjakarta Service : an Exploratory Data Analysis"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "d6ffc586-354f-484f-8119-4dfbf6a74b8f",
   "metadata": {},
   "source": [
    "This project delves into the data analytics of Transjakarta's operations, exploring patterns in ridership, passenger profiles, and areas for potential improvement. By leveraging data insights, the aim is to enhance the efficiency and effectiveness of this critical public service."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "41646e13-08df-4fc2-8a82-d1a0a239a9af",
   "metadata": {},
   "source": [
    "### Business Problem"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "d88c7736-44f8-4b55-8a3d-154d6246c9a1",
   "metadata": {},
   "source": [
    "PT Transjakarta's objective is to offer a safe and comfortable journey for all its users. To improve the service, PT Transjakarta is seeking to identify any specific patterns in its user data that could be leveraged as insights for futher improvements and developments."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "af0cded6-23b9-4c54-8bff-42508540262f",
   "metadata": {},
   "source": [
    "### Business Questions"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "8ac061af-9de5-4d4f-886e-e925ac0f41ab",
   "metadata": {},
   "source": [
    "Patterns of the journeys.\n",
    "* What is the average journey duration of Transjakarta users?\n",
    "* When does the level of usage increase and by how much?"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "08ea2b17-5ceb-4fa3-b895-abd55503f2e4",
   "metadata": {},
   "source": [
    "Corridor-specific patterns\n",
    "* Which corridors are the busiest?\n",
    "* Is the corridor bus capacity adequate?\n",
    "* What can be done to improve the service?"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "23d1c300-be72-415e-a2f9-61913bed57eb",
   "metadata": {},
   "source": [
    "Bus stop-specific patterns\n",
    "* Which bus stops are the busiest?\n",
    "* How to improve services at bus stops?"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "b0b0d1c2-0c0b-462f-b2c2-b534175e46d5",
   "metadata": {},
   "source": [
    "Information regarding the characteristic patterns of the users:\n",
    "* By gender: What is the ratio of female to male users?\n",
    "* By age: What is the age of the majority of users? Are there elderly users?\n",
    "* What can be done to improve the journey for the elderly?"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "ba0ab9b2-ecd2-43c1-ae2d-497e1b95afb0",
   "metadata": {},
   "source": [
    "**Key Questions**:  How can we optimize the performance of Transjakarta's fleet, facilities, and operational aspects? "
   ]
  },
  {
   "cell_type": "markdown",
   "id": "cf30b951-ee26-465b-bfc0-84cc0cf25d61",
   "metadata": {},
   "source": [
    "### Dataset"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "66c55822-e2c5-4bfc-b136-79bd7657342f",
   "metadata": {},
   "source": [
    "1. transID : Unique transaction id for every transaction\n",
    "2. payCardID : Customers main identifier. The card customers use as a ticket for entrance and exit.\n",
    "3. payCardBank : Customers card bank issuer name\n",
    "4. payCardName : Customers name that is embedded in the card.\n",
    "5. payCardSex : Customers sex that is embedded in the card\n",
    "6. payCardBirthDate : Customers birth year\n",
    "7. corridorID : Corridor ID / Route ID as key for route grouping.\n",
    "8. corridorName : Corridor Name / Route Name contains Start and Finish for each route.\n",
    "9. direction : 0 for Go, 1 for Back. Direction of the route.\n",
    "10. tapInStops : Tap In (entrance) Stops ID for identifying stops name\n",
    "11. tapInStopsName : Tap In (entrance) Stops Name where customers tap in.\n",
    "12. tapInStopsLat : Latitude of Tap In Stops\n",
    "13. tapInStopsLon : Longitude of Tap In Stops\n",
    "14. stopStartSeq : Sequence of the stops, 1st stop, 2nd stops etc. Related to direction.\n",
    "15. tapInTime : Time of tap in. Date and time\n",
    "16. tapOutStops : Tap Out (Exit) Stops ID for identifying stops name\n",
    "17. tapOutStopsName : Tap out (exit) Stops Name where customers tap out.\n",
    "18. tapOutStopsLat : Latitude of Tap Out Stops\n",
    "19. tapOutStopsLon : Longitude of Tap Out Stops\n",
    "20. stopEndSeq : Sequence of the stops, 1st stop, 2nd stops etc.Related to direction.\n",
    "21. tapOutTime : Time of tap out. Date and time\n",
    "22. payAmount : The number of what customers pay. Some are free. Some not. are free. Some not."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "731a2e7c-1b13-4b4b-8497-c946bdeb953b",
   "metadata": {},
   "source": [
    "### Analysis Framework"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "347a006b-1842-4632-9ea8-43eb226b9737",
   "metadata": {},
   "source": [
    "* Trip Duration\n",
    "* Trip Frequency\n",
    "* Ridership Pattern : Corridor\n",
    "    * Busiest corridors during peak hours \n",
    "* Ridership Pattern : Tap-in and Tap-out Stops\n",
    "    * Busiest bus stop during peak hours\n",
    "* Demographic : Gender\n",
    "* Inclusivity : Service for elderly"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "23ea5f21-7f30-4ecc-a66f-be5511130267",
   "metadata": {},
   "source": [
    "For more visualization please visit this link:  https://public.tableau.com/app/profile/lucia.pramanti/viz/CapstoneModul2-Lucia/Dashboard1"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "d8b3246b-5a5b-4948-8ce1-e4f86fe01351",
   "metadata": {},
   "source": [
    "Presentation file can be found at this link : https://www.canva.com/design/DAGKe7WozgA/cFaATmsgfxrtT660c9DAGg/view?utm_content=DAGKe7WozgA&utm_campaign=designshare&utm_medium=link&utm_source=editor"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.11.7"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
