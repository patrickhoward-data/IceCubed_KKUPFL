# Ice Time Impact Index: Ice^3 (Ice Cubed) - A Measure of Player Impact in Ice Hockey
Introduction
The Ice Time Impact Index, (III) referred to as Ice^3 (pronounced "Ice Cubed"), represents a weighted measure of a hockey player's on-ice performance adjusted for the time they spend on the ice. This metric aims to quantify a player's contribution to the team per minute of ice time, offering insights into a player's efficiency and overall impact on the game. 


Components and Weights
The Ice^3 value for a player is computed by considering several statistical elements of a player's performance, each weighted differently to reflect its relative importance:
•	Goals: Weighted at 4.5
•	Assists: Weighted at 3
•	Shots: Weighted at 0.5
•	Hits: Weighted at 0.25
•	Blocks (Blk): Weighted at 0.5
These weights can be adjusted based on more intricate analyses or domain-specific knowledge, but the provided weights serve as a foundational guideline. (These weights are specific to KKUPFL) 


Calculation
To compute the Ice^3 value for a player:
1.	Multiply each component by its respective weight.
2.	Sum up these weighted values.
3.	Divide by the player's Time On Ice (TOI).
Mathematically:

![image](https://github.com/patrickhoward-data/IceCubed_KKUPFL/assets/104926142/1e20e153-8795-4357-8a10-e1284a8ac32e)

 
Data Representation in Database
Data is stored in a SQL Server table named _skaters_2023 with the following columns:
•	Player: Name of the player.
•	TOI: Time On Ice in minutes.
•	Goals: Number of goals scored by the player.
•	Assists: Number of assists made by the player.
•	Hits: Number of hits made by the player.
•	Blk (Blocks): Number of blocks made by the player.
•	Shots: Number of shots taken by the player.
•	IceCubed: Computed Ice^3 value for the player.

It's crucial to note that the TOI is stored in minutes in the database. This ensures that the Ice^3 calculation is accurate, as it uses TOI directly without needing any conversion.

Data Retrieval and Analysis

SQL queries facilitate both the calculation and retrieval of Ice^3 values for players in the database. The main components include:
1.	Computing the average TOI for the league and filtering players based on this.
2.	Ordering players by their Ice^3 values to identify top performers.
3.	Incorporating the Ice^3 calculation directly into SQL Server for efficiency and consistency.
For practical purposes, avoid using special characters in column names for easier SQL querying and database portability.

