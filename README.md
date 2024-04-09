# Group 2 MIST 4610 Project 1

## Group Name:
21479 Group 2

## Team Members:
1. Leonardo Hodis (@Leonardo-Hodis)
2. Chris Bohr (@ChrisBohr)
3. Alphin Philip (@alphinphilip1)
4. Prathu Garg (@Prathulu)
5. Indhu Madineni (@indhu0614)

## Problem Description:
The given task is to model and build a relational database that stores useful and necessary information for the manager of a football club. The main entities in the model are the Players and Teams entities. "Players" refers to each of the individuals that participate in games and "Teams" refers to the grouping of specific players together. For each player, there is a record of their contract, game statistics, medical history, and brand deals. Moreover, all teams have distinct sponsorships, coaches, practices, games, etc. Our goal is to effectively and efficiently model these various relationships, create sample data, and use said data to populate all of the entities and their attributes. Additionally, we need to construct functioning queries on this data in order for us to obtain valuable insight about how the club operates 
in a manner that is relevant from a managerial perspective.

## Data Model:
This data model is based on the structure of a hypothetical football club. The 'Players' entity represents each of the individuals that play on the football teams. Each player has a single contract and each contract is designated for a single player, so we placed a one-to-one relationship between these two entities.

Apart from the 'PlayerContracts' entity, the 'Players' entity has three other branches extending from it. The 'Medical Records' entity represents the health and patient history of each player. It includes information on types of injuries, when they occurred, whether they have recovered, and their expected return date to the team. Each player can have multiple medical records, such as records from different healthcare providers, but each medical record will only correspond to a single player. Hence, we established a one-to-many relationship between the 'Players' and 'Medical Records' entities. Similarly, we put a one-to-many relationship between 'Players' and 'Brand Deals' since one player can have brand deals with multiple brands. 

The 'PlayerStats' entity stores information about the performance of each player during their games, such as the number of points, assists, and rebounds they amassed. Each player will have more than one set of statistics that are unique to them. These sets are gathered after every game, so there is a one-to-many relationship between the 'Players' and 'PlayerStats' entities as well as a one-to-many relationship between the 'Games' and 'PlayerStats' entities.

The 'Teams' entity consists of the various teams within the club which are made up of many different players. Similar to the one-to-one relationship between the 'Players' and 'PlayerContracts' entities, each team has its own coach and each coach is in charge of one team. All coaches also have their own contracts. Additionally, teams have different sponsporships and merchandise to promote themselves and raise money for things like equipment. 

![Screenshot 2024-04-04 at 5 30 14 PM](https://github.com/indhu0614/MIST_GP/assets/165066443/f2696c51-ba17-4f1a-bc0f-0aa15eb62e79)

## Data Dictionary: 
<img width="902" alt="Screenshot 2024-03-30 at 4 31 31 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/04caab77-1f31-4ac9-a504-525aec266f70">

<img width="893" alt="Screenshot 2024-03-30 at 4 32 06 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/39ca2528-21c5-40e1-9b64-fbcce74687a8">

<img width="871" alt="Screenshot 2024-03-30 at 8 50 20 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/4fa35d30-8d81-46cb-8a6d-72be935f10e5">

<img width="602" alt="Screenshot 2024-03-30 at 8 50 32 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/d290ca46-4751-486d-bfb0-bf038139ca23">

<img width="698" alt="Screenshot 2024-03-30 at 4 37 38 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/581ea3be-65b8-4822-9b75-3e8c6978fd1a">

<img width="587" alt="Screenshot 2024-03-30 at 8 53 13 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/21d6692a-3426-4336-856f-0959207fe120">

<img width="588" alt="Screenshot 2024-03-30 at 8 53 19 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/faf92e8c-8524-4913-8f6a-2d1f172e757e">

<img width="685" alt="Screenshot 2024-03-30 at 4 37 49 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/e391799d-31f5-4bbb-af18-c1702066416b">

<img width="589" alt="Screenshot 2024-03-30 at 8 53 28 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/d5314a93-e36c-4f9a-aeed-d371c188422a">

<img width="588" alt="Screenshot 2024-03-30 at 8 53 35 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/888b1e5f-e3c6-4487-b122-62d5a75c2e9d">

<img width="597" alt="Screenshot 2024-03-30 at 8 53 41 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/177e1d9d-85d3-49a8-81e4-a4770a4c1303">

<img width="587" alt="Screenshot 2024-03-30 at 8 53 48 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/ef517d62-3eb6-4caf-99e3-3626303a6fe6">

<img width="590" alt="Screenshot 2024-03-30 at 8 53 53 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/d0ff946b-b4f7-4ba4-ba66-c947ac98abe3">

<img width="588" alt="Screenshot 2024-03-30 at 8 54 00 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/98f65bb7-d46a-4180-be16-2df947660995">

<img width="591" alt="Screenshot 2024-03-30 at 8 54 06 PM" src="https://github.com/indhu0614/MIST_GP/assets/165066443/edff218d-9973-4cb4-bb5d-ddba819b3f93">

## Queries:

1.) List of all players with their teams.  


Description: A manager can use this information to quickly see the roster of players and their respective teams, which is fundamental for organization and team management.

Query 1 lists each individual player with their respective team. Query 1 allows managers to automatically list players and their teams in alphabetic order rather than having to manually scan the roster for each individual player. A manager can use this information to quickly see the roster of players and their respective teams, which is fundamental for organization and team management.

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/8c59d08c-ce70-4671-aa11-42468495e985)

2.) Total amount spent on player contracts 

Description: This helps a manager understand the financial commitments of the organization to player salaries, which is crucial for budgeting and financial planning.

Query 2 displays the total amount of how much was spent on each players contract. This allows the managers to see the financial commitment of each player on the sports league relative to their salaries. This query will be very useful in future budget allocations as well as general financial planning.

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/2a179dbe-1e5a-4fbb-ba50-fed4366e38ce)

3.) Current brand deals 

Description: A manager can assess the value and number of active brand deals, an important aspect of revenue stream analysis.

Query 3 displays all of the current active brand deals as well as how much they are valued at. This query conveniently organizes the brand deals so the managers will not have to manually sift through their sponsorships. This query allows managers to analye their current brand deals as well as make decisions on future brand deals which is an important aspect of revenue stream analysis.

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/f9f8f833-4e02-4cfb-b8aa-6b64123cbb17)

4.) Retrieve all equipment types and their count. 

Description: Managers need to keep track of the equipment inventory to ensure that there are enough supplies for training and matches.

Query 4 displays each type of equipment as well as their count. Query 4 allows managers to keep track of the equipment inventory to ensure that there are enough supplies for training and matches. This query helps in inventory management and future procurement planning.

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/ad1fc273-8202-4f1a-836f-c95ffdab1563)

5.) Average attendance per game 

Description: Understanding the average attendance can help a manager gauge fan engagement and the success of marketing efforts for game days.

Query 5 displays how many tickets have been sold respective to each game. This query allows managers to automatically compare how many seats there are and how many tickets are being sold. Understanding the average attendance can help a manager gauge fan engagement and the success of marketing efforts for game days. 

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/a554e12f-e0ec-46c5-b6f1-e3fcdca8507d)

6.) Players with injury status and expected return dates

Description: Managers need to be aware of the health status of players to make informed decisions about team lineup and player workload.

Query 6 displays each player with an injury as well as what the expected date they will be able to return is. Query 6 allows managers to see which players will be unavailable for certain periods of time all in one place, rather than having to look at each player individually.  Managers need to be aware of the health status of players to make informed decisions about team lineup and player workload.

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/98bade27-c66d-4a4a-ad5e-4de2b9aabc5b)

7.) Teams with more away than home wins 

Description: Identifies teams with stronger performance in away games, which could indicate resilience and inform strategic decisions regarding training and preparation for different venues.

Query 7 displays all the teams that have more wins when they play away games versus when they play home games. This query saves managers the time of having to manually separate which games are which for each team. Query 7 identifies teams with stronger performance in away games, which could indicate resilience and inform strategic decisions regarding training and preparation for different venues. 

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/72ebbab8-93b1-40f4-9467-6f66af149676)

8.) Total merchandise sales per team 

Description: Merchandise sales are a significant source of revenue. By knowing the sales per team, managers can assess the popularity and marketability of each team and decide where to focus marketing efforts.

Query 8 displays the total merchandise sales of each team. This query organizes all the teams sales in order rather than having the user need to manually compare each team side by side. Merchandise sales are a significant source of revenue. By knowing the sales per team, managers can assess the popularity and marketability of each team and decide where to focus marketing efforts. 

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/e934f3bd-001d-451b-81c0-39024df8f538)

9.) Most effective players based on points per game 

Description: This query identifies players who are scoring above the average points per game, which is essential for a manager to understand who the key contributors are on the court and to potentially use this information for starting lineups or in player development programs.

Query 9 displays which players are the most efficient and have the highest points per game. Managers can use this query to organize the stats for all the players rather than having to calculate the points per game for each individual player. This query identifies players who are scoring above the average points per game, which is essential for a manager to understand who the key contributors are on the court and to potentially use this information for starting lineups or in player development programs.

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/2ceab114-0e2e-4a1d-bc04-bc7018492f9d)

10.) Total points scored by players per team 

Description: High total points can indicate a strong offensive team, while lower points might highlight a need for strategic or player changes.

Query 10 displays the sum of all the points scored by the players on each team. Managers can organize these stats rather than having to manually calculate this for each of their teams. This query is essential for managers to analyze the overall performance of their teams in terms of scoring. High total points can indicate a strong offensive team, while lower points might highlight a need for strategic or player changes. 

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/c4db2a5d-5abe-460f-bc3b-38828d06b76f)

## Matrix

![image](https://github.com/alphinphilip1/MIST4610-Project-1/assets/166083116/8d2501b4-8bcb-4bfa-8664-90d9f21c31d0)
