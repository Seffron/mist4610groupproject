# mist4610groupproject
# MIST 4610 Group Project: Group 7

## Team Name and Members:
Team Name: Group 7

Team Members:
1. Audrey Staples - https://github.com/audreystaples/mist4610groupproject 
2. Angela Ren - https://github.com/angelaaa456/mist4610groupproject 
3. Sammy Effron - 
4. Tanner Sutherland - https://github.com/tannersutherland/mist4610groupproject
5. Tyler Schildkraut - https://github.com/tylerschildkraut/MIST-4610-Project-Group-7

# Scenario Description:
We wanted to construct a data model that organizes key information used to navigate the NCAA college football landscape. The ultimate goal for our model is to represent the various relationships that exist among Coaches, Teams, Players, Rosters, Games, etc. in a way that mirrors how real NCAA programs operate. Although our data is hypothetical, it represents pertinent information that would meet managerial requirements within the NCAA ecosystem. From surveying game statistics to determining player status on a roster, our database provides insights that would prove highly useful to NCAA stakeholders. Ultimately, we aimed to create a database that would effectively aid managerial decision making within essential business units such as logistics management, decision-making, and reporting within an ever evolving industry.

# Data Model:
<img width="446" height="512" alt="Datamodel" src="https://github.com/user-attachments/assets/01b3a6f2-24fd-4248-b281-8c5350cc9420" />

**Explanation**: Our database is based on the NCAA with hypothetical data included for ease of data insertion. For instance, instead of the University of Georgia the record is the Athens Bulldogs.

Beginning with the Teams entity, we made teamID our identifier and included attributes such as teamName and conference. This entity relates to our Coaches entity with a one-to-many relationship because teams have many coaches, but those coaches are linked to only one team. Our Coaches entity is identified by the primary key coachID and contains attributes such as name, role which describes their specific coaching position (Head Coach, Offensive Coordinator, etc.), yearsOfExperience describing the amount of years of coaching experience they have, as well as a foreign key being teamID. Rosters represent the associative entity connecting the many-to-many relationship between Teams and Players as players can be on many teams and teams are composed of many players. Rosters are identified by rosterID, and they have attributes such as a foreign keys playerID and teamID. Additionally, Rosters display the startDate of a player’s commitment to a team as well as the endDate which could be null if the player is still playing on that team playing. Rosters also display the player’s position on that specific team as well as their jersey number on that specific team. The Players entity is identified by a unique playerID which is the primary key of that entity. In addition to that, the Players entity has attributes such as name, the player’s yearInSchool, their height in inches, their weight in pounds, and the status of their scholarship, if applicable. Additionally, the Players entity has a one-to-many relationship with the entity named Injuries as players can have many injuries but a specific instance of an injury can only occur once in one player. Injuries have the primary key injuryID along with attributes such as injuryName, lengthOfRecovery, surgery name if needed, as well as the foreign key playerID which specifies the one-to-many relationship.

Moving on to another key entity, we have Games. Games are identified by their primary key which is called gameID. Our Teams table has two one-to-many relationships with the Games entity meaning that one instance of a team (the home team) has many games but those games only have one home team. Additionally, another instance of a team (the away team) also has many Games but those specific games are only related to one away team. For that reason, our Games entity contains two foreign keys from the Teams table, one being homeTeamID and the other being awayTeamID. Another foreign key in the Games table is the stadiumID. The last attribute in the Games table is the date attribute which specifies the date the game occurred on. Our Stadiums table is connected to the Games entity by a one-to-many relationship. Stadiums house many games but those games can only be played at one stadium at a time. Stadiums are also identified by attributes such as stadiumName, city, and capacity. Stadiums also have a one-to-many relationship with Seats because a stadium has many seats but a seat can only be in one stadium. Seats have the primary key seatID as well as attributes like section, row, seatNumber, seatType, and the foreign key stadiumID. Seats also have a one-to-many relationship with Tickets as a seat can be sold by many tickets but tickets only are attached to one seat. Tickets are identified by ticketID, and have attributes such as price, ticketHolderName, the foreign key gameID, and the foreign key seatID. This then brings about the relationship between Games and Tickets being one-to-many as games have many tickets but a specific ticket is only attached to one game. The last entity that needs describing is our Statistics entity. Statistics has a many-to-one relationship with Players as Players have many statistics but a specific statistic is only connected to one player. Another relationship that exists with Statistics is a many-to-one relationship with Games. Statistics are present in many games, but a game only has one instance of a specific player statistic. Statistics are identified by a statID, a foreign key of playerID, yards if applicable, touchdowns if applicable, tackles if applicable, interceptions if applicable, receptions if applicable, fieldGoals if applicable, as well as the foreign key gameID.

# Data Dictionary:
<img width="1600" height="557" alt="coaches" src="https://github.com/user-attachments/assets/ef48fef1-49db-4bef-87a4-b6572cb34a0f" />
<img width="497" height="213" alt="players" src="https://github.com/user-attachments/assets/8963047a-d904-48cb-b689-804a69d1cb1e" />
<img width="487" height="253" alt="rosters" src="https://github.com/user-attachments/assets/682d80c5-5505-4bb6-be92-ac6a9efe3a8d" />
<img width="509" height="238" alt="injuries" src="https://github.com/user-attachments/assets/b1e04a06-4ff8-4672-b708-e9358d80e5cf" />
<img width="482" height="340" alt="stats" src="https://github.com/user-attachments/assets/44b7e177-32c6-4fe3-8776-67410bb6bfbe" />
<img width="485" height="142" alt="teams" src="https://github.com/user-attachments/assets/ac98d08d-916c-4f19-965a-7532eeb96b2c" />
<img width="1600" height="604" alt="games" src="https://github.com/user-attachments/assets/7a64b5e7-2709-4ea9-9e17-e0750b96009c" />
<img width="1600" height="446" alt="stadiums" src="https://github.com/user-attachments/assets/7a146324-3266-4c72-98ce-d6e1411d5fc5" />
<img width="1600" height="674" alt="seats" src="https://github.com/user-attachments/assets/006a95ba-43eb-4ebb-9e68-4b8a583729d1" />
<img width="1600" height="691" alt="tickets" src="https://github.com/user-attachments/assets/3a4d82b3-5afe-4cb0-bc0c-455f3c30ab68" />



# Queries:
<img width="508" height="250" alt="querymatrix" src="https://github.com/user-attachments/assets/ddbe963f-a644-4d4c-bc0e-93de9f360365" />

Query 1: Number of Players on Each Team

<img width="565" height="181" alt="query1" src="https://github.com/user-attachments/assets/8f3428e4-c2ea-447d-9fd2-92327a59666b" />
<img width="388" height="588" alt="query1results" src="https://github.com/user-attachments/assets/6fec1599-57ee-4366-a729-1df1015bcc06" />

Description: 
This query shows every team and counts how many players are currently listed on their roster. It joins the Teams and Rosters tables using the teamID to associate players with their teams, then groups the results by each team name.

Managerial Justification:
Roster size directly affects scholarship budgeting, recruiting needs, and practice planning. Athletic departments can use this information to verify roster compliance with NCAA limits (e.g., 85 scholarship players in Division I football) and identify whether certain teams are under- or over-staffed. It also provides insights for coaching staff to balance positional depth across the roster.

Query 2: Total Yards Per Player

<img width="709" height="180" alt="query2" src="https://github.com/user-attachments/assets/6bc3e85f-1173-49f5-b657-8825c8ed26f3" />
<img width="274" height="639" alt="qurey2results" src="https://github.com/user-attachments/assets/1c2eb7bc-240a-4519-bc02-f4f3fd47bd81" />

Description: 
Calculates the total number of offensive yards gained by each player across all games using the Statistics table. The query groups by player name and sums their yards column, returning players in descending order of total yardage.

Managerial Justification:
Tracking cumulative yardage helps offensive coordinators evaluate player impact and consistency. This data is key for determining award nominations, highlighting top performers in media relations, and identifying players who may deserve more playing time or position adjustments based on productivity.

Query 3: Players Without Recorded Statistics

<img width="622" height="141" alt="query3" src="https://github.com/user-attachments/assets/3086b749-9761-4f6d-817f-a6727a7ae53c" />
<img width="243" height="570" alt="query3results" src="https://github.com/user-attachments/assets/6b43cdba-f0d7-4718-a8b3-d08bff9ab600" />

Description: 
Identifies all players who have not yet recorded any game statistics by checking which player IDs are not present in the Statistics table.

Managerial Justification:
This helps coaching staff and analysts find players who have not appeared in any games and make decisions about those players accordingly. Managers can use this information to determine which players may need more opportunities to play or to address what to do with those players in the future.

Query 4: Players with Multiple Recorded Injuries

<img width="622" height="186" alt="query4" src="https://github.com/user-attachments/assets/f98b23c5-d0cc-4497-9488-ab05b36d2bf6" />
<img width="292" height="471" alt="query4results" src="https://github.com/user-attachments/assets/da3c34af-f3d9-4414-a967-ba408acacddc" />

Description: 
Displays all players who have sustained more than one recorded injury. It joins Players and Injuries using playerID, groups the results by player, and filters using a HAVING clause.

Managerial Justification:
Identifying players with frequent injuries allows medical staff to implement personalized recovery or training programs. Coaches can use this information to manage playing time and avoid re-injury, which reduces long-term risk and protects the team’s investment in scholarship athletes.

Query 5: Average Player Weight by Position

<img width="705" height="157" alt="query5" src="https://github.com/user-attachments/assets/980b2b71-16dd-44a1-9bb1-de2413ebba51" />
<img width="244" height="411" alt="query5results" src="https://github.com/user-attachments/assets/9e5288f8-ed49-4859-a0a7-04faa0751a93" />

Description: 
Finds the average weight of players for each position across all rosters. It joins Rosters and Players and groups the results by position.

Managerial Justification:
Weight and conditioning benchmarks are crucial for maintaining competitiveness. This data helps strength and conditioning coaches monitor whether players at each position (e.g., linemen, receivers, linebackers) meet desired physical standards and make training adjustments if a position group is under or over target weight ranges. AI was utilized here to locate the backticks function which allowed for the system to not confuse the parentheses in the column title with SQL script parentheses.

Query 6: Total Games Played by Each Team

<img width="909" height="168" alt="query6" src="https://github.com/user-attachments/assets/0310e7b9-133d-4b0b-ab78-f4bfae65e6e9" />
<img width="376" height="658" alt="query6results" src="https://github.com/user-attachments/assets/2a878bb4-614b-4fc0-b008-bee8e2e7ff62" />

Description: 
Shows the number of total games each team has participated in—both home and away. It joins Teams and Games and counts how many times a team appears as either the home or away team.

Managerial Justification:
Tracking total games played helps administrators measure team activity levels across the season and can highlight scheduling imbalances. Operations teams can use this data to evaluate travel frequency, ensure scheduling fairness, and make logistical improvements for future seasons.

Query 7: Current Scholarship Players

<img width="498" height="166" alt="query7" src="https://github.com/user-attachments/assets/c3e6689e-48f2-4cff-b7e6-ddd19e8f1e18" />
<img width="450" height="592" alt="query7results" src="https://github.com/user-attachments/assets/ea007fc8-c5ed-4a62-bae7-34ea45d317a4" />

Description: 
Lists all players who currently receive full athletic scholarships, ordered alphabetically by name.

Managerial Justification:
Scholarship allocation is one of the largest financial responsibilities for athletic programs. This query helps compliance officers ensure that scholarship funds are properly assigned and enables administrators to monitor financial obligations and renewal cycles.

Query 8: Longest Recovery Injuries

<img width="571" height="132" alt="query8" src="https://github.com/user-attachments/assets/ca480382-7037-4935-b034-73e9441ac567" />
<img width="375" height="607" alt="query8results" src="https://github.com/user-attachments/assets/25ee7bc8-7295-4eed-8484-ec5e4b2d670a" />

Description: 
Displays the injuries in the database with the longest reported recovery times, ordered from longest to shortest.

Managerial Justification:
Provides insight into which types of injuries are most severe and time-consuming to heal. This allows sports medicine staff to plan future prevention programs, identify potential insurance or cost implications, and communicate expected recovery timelines to coaches and media. Although we had not yet learned this feature, we utilized AI to accomplish this query as the VARCHAR() data format is not compatible with the ORDER BY DESC or ASC capabilities. Utilizing CAST and UNSIGNED, our string data values were converted to numbers effectively.

Query 9: Average Tickert Price Per Game

<img width="1090" height="156" alt="query9" src="https://github.com/user-attachments/assets/98016203-b2e0-4340-b096-d3e95449d347" />
<img width="243" height="597" alt="query9results" src="https://github.com/user-attachments/assets/113f233b-b18b-4924-9977-4e522dd931ae" />

Description: 
Calculates the average price of tickets sold for each game by joining the Games and Tickets tables and grouping results by gameID.

Managerial Justification:
Understanding average ticket prices helps the marketing and sales department assess revenue potential per game. It also reveals which matchups draw higher-paying audiences, allowing pricing strategies to be adjusted for rivalry or high-demand games to maximize profits. Similarly as before, we utilized the CAST function so that we could convert the original VARCHAR value of the price attribute in the Tickets entity to DECIMAL data formats so that we would be able to perform aggregations on the values.

Query 10: Top 5 Players by Touchdowns Scored

<img width="687" height="196" alt="query10" src="https://github.com/user-attachments/assets/e3f9449f-5607-472d-9575-765fa4025012" />
<img width="342" height="291" alt="query10results" src="https://github.com/user-attachments/assets/7fa638dd-dfeb-4da4-8403-eca4b0a601d1" />

Description: 
Lists the five players with the highest total touchdowns recorded across all games.

Managerial Justification:
This helps highlight standout offensive players for performance evaluations, awards, and media recognition. Teams can also use this information for recruiting promotions and identifying which athletes consistently contribute to scoring. The LIMIT 5 function, which we learned through use of AI, allowed us to locate the top 5 players worth considering.
