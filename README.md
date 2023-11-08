# 4610-Project---Ryan-Burstiner
# Group Project 1

Dylan Vila, Jonathan Gilbertson, Robert Delorme, Ryan Burstiner, Brett Serwin


## Problem Description
As the owner and operator of a soccer club, my business is centered around the management and operation of a professional soccer team. Our club competes in a prominent soccer league and participates in various competitions at the national and international levels. We aim to be a successful and well-recognized soccer club, both on and off the field. Here is an overview of our organization:
Teams 
We have multiple teams, including senior, reserve, and youth teams.
Each team has a roster of players with details such as name, age, nationality, position, and jersey number.
Players can move between teams, and transfers or loan deals may occur
Players:
Each team has a roster of players with details such as name, date of birth, nationality, position, salary
Matches:
The teams participate in matches 
Each match includes the date, time, opponent, venue, and match results
Stadium:
Our teams have stadiums which multiple teams can play in 
Each stadium has details such as city, state, capacity, name and the year it was built
Coaching Staff:
Our coaching staff includes head coaches, assistant coaches, and other support staff.
Coaches have their profiles, including name, title, salary, and date of birth.
Club Staff and Management:
Non-playing staff, such as administrators, medical personnel, and management, are vital to our operation.
We need to keep track of their titles, roles, name, salary, and date of birth.
Sponsors and Partnerships:
We have partnerships and sponsorships with various companies and organizations.
Details about these partnerships, contracts, and sponsorship agreements are important.
Injuries and Medical Records:
Monitoring and managing player injuries and medical histories is crucial for player well-being and performance.
Team Kits:
We have multiple kits for each team
Details about the kit name, and type are important for keeping track of when to wear one 
Finances:
Managing the club's finances is crucial. This includes revenue from ticket sales, merchandise, and sponsorships, as well as expenses related to player contracts, staff salaries, and operational costs.




The database project will be crucial for us to manage these aspects effectively. The MIST 4610 class from the University of Georgia will play a critical role in designing a relational database that can efficiently store and retrieve information related to our club's various entities, attributes, and relationships. We need a database that ensures data accuracy, security, and accessibility for different club stakeholders, including management, coaches, players, and fans.


## Data Model
<img width="454"<img width="969" alt="Screen Shot 2023-11-07 at 9 41 52 PM" src="https://github.com/ryanburst1/4610-Project---Ryan-Burstiner/assets/148258130/e14e9300-6ddf-4f7d-a948-389439b1acff">

## Data Dictionary 

| Entity Name   | Column Name       | Description                                       | Data Type and Length |
|---------------|-------------------|---------------------------------------------------|-----------------------|
| Coach         | coachID           | Unique identification number for each coach (PRIMARY KEY) | INT                 |
| Coach         | coachFname        | First name of each coach                         | VARCHAR(45)          |
| Coach         | coachLname        | Last name of each coach                          | VARCHAR(45)          |
| Coach         | title             | Title of each coach                              | VARCHAR(45)          |
| Coach         | salary            | Salary of each coach                             | INT                 |
| Coach         | dob               | Date of birth for each coach                     | DATE                |
| Coach         | Teams_teamID      | The teamID for the team they are the coach for (FOREIGN KEY) | INT                 |
| Costs         | costID            | The unique ID for each specific cost (PRIMARY KEY) | INT                 |
| Costs         | Teams_teamID      | The teamID for the team that is the source of each cost (FOREIGN KEY) | INT                 |
| Costs         | costType          | The type of each cost                            | VARCHAR(45)          |
| Injury        | InjuryID          | Unique identification number for each injury (PRIMARY KEY) | INT                 |
| Injury        | injuryType        | Describes the area of the body where the injury occurred | VARCHAR(45)          |
| Injury        | Matches_matchID   | The matchID for the match when the injury occurred (FOREIGN KEY) | INT              |
| Injury        | Player_playerID   | The playerID for the player who got injured (FOREIGN KEY) | INT              |
| Kits          | kitsID            | The unique ID of the kit (PRIMARY KEY)           | INT                 |
| Kits          | kitName           | The name of the kit                              | VARCHAR(45)          |
| Kits          | kitType           | The style of jersey each kit is                   | VARCHAR(45)          |
| Kits          | Teams_teamID      | The ID of the team that wears the kit (FOREIGN KEY) | INT                 |
| Matches       | matchID           | Unique identification number for each match (PRIMARY KEY) | INT              |
| Matches       | opponent          | Lists the name of the opponent our club’s team faced that match | VARCHAR(45)    |
| Matches       | date              | Lists the date that the match was played         | DATE                |
| Matches       | result            | Lists the result of the match from our club’s perspective (win, loss, or draw) | VARCHAR(45) |
| Matches       | Teams_teamID      | The teamID for the team of our club that played in the match (FOREIGN KEY) | INT         |
| Matches       | Stadium_stadiumID | The stadiumID for the stadium where the match was played (FOREIGN KEY) | INT             |
| Players       | playerID          | The unique ID of the player (PRIMARY KEY)        | INT                 |
| Players       | firstName         | The first name of each player                    | VARCHAR(45)          |
| Players       | lastName          | The last name of each player                     | VARCHAR(45)          |
| Players       | dateOfBirth       | The date of birth of each player                  | VARCHAR(45)          |
| Players       | position          | The position played by each player                | VARCHAR(45)          |
| Players       | nationality       | Country of origin for each player                | VARCHAR(45)          |
| Players       | salary            | The salary of each player                        | INT                 |
| Players       | Teams_teamID      | TeamID of the team that the player plays for (FOREIGN KEY) | INT                 |
| Players       | Players_playerID  | The playerID of the player that is the mentor for the player whose playerID is the primary key of the row (ONE TO MANY RECURSIVE) | INT |
| Revenues      | revenueID         | The unique ID of the specific revenue stream (PRIMARY KEY) | INT              |
| Revenues      | revenueType       | Type of revenue for each specific revenue stream  | VARCHAR(45)          |
| Revenues      | revenueAmount     | The dollar value brought in by the specific revenue stream | INT              |
| Revenues      | Teams_teamID      | The teamID of the team that is responsible for generating each specific revenue stream (FOREIGN KEY) | INT |
| Sponsor       | sponsorID         | The unique ID of the sponsor (PRIMARY KEY)        | INT                 |
| Sponsor       | sponsorName       | Name of sponsor                                  | VARCHAR(45)          |
| Sponsor       | amountReceived    | Amount of money received from each sponsor       | INT                 |
| Sponsor       | contractLength    | Length of each sponsorship contract               | INT                 |
| Stadium       | stadiumID         | The unique identification number for each stadium (PRIMARY KEY) | INT             |
| Stadium       | city              | The city where each stadium is located            | VARCHAR(45)          |
| Stadium       | state             | The state where each stadium is located           | VARCHAR(45)          |
| Stadium       | capacity          | How many spectators can fit in each stadium for a given match | INT           |
| Stadium       | stadiumName       | The name of each stadium                          | VARCHAR(45)          |
| Stadium       | yearBuilt         | The year each stadium was built                   | VARCHAR(45)          |
| Team_Staff    | staffID           | The unique identification number for each staff member (PRIMARY KEY) | INT          |
| Team_Staff    | title             | Title of each staff member                         | VARCHAR(45)          |
| Team_Staff    | staffFname        | First name of each staff member                    | VARCHAR(45)          |
| Team_Staff    | staffLname        | Last name of each staff member                     | VARCHAR(45)          |
| Team_Staff    | salary            | Salary of each staff member                        | INT                 |
| Team_Staff    | dob               | Date of birth of each staff member                 | DATE                |
| Team_Staff    | Teams_teamID      | The teamID for the team they are a staff member for (FOREIGN KEY) | INT             |
| Teams         | teamID            | The unique identification number for each team in our club (PRIMARY KEY) | INT          |
| Teams         | teamName          | The name of each team in our club (all teams go by our club name of FC Salge) | VARCHAR(45) |
| Teams         | teamLevel         | Gives the level each team plays at                 | VARCHAR(45)          |
| Teams         | Stadium_stadiumID | Lists the home stadium for each team (FOREIGN KEY) | INT                 |
| Teams_has_Sponsor | teamsponsorID   | The unique ID of the pairing of the team and sponsor (PRIMARY KEY) | INT             |
| Teams_has_Sponsor | Teams_teamID   | The unique ID of the team being sponsored (FOREIGN KEY) | INT                |
| Teams_has_Sponsor | Sponsor_sponsorID | The unique ID of the sponsor (FOREIGN KEY)       | INT                 |


## Ten Queries

Query 1: Find the salary distribution by position for each team where the total salary for the position group is greater than $500,000

Justification: This query gives us data that can be used by the front office of the club to decipher which position groups are being paid the most money, and how much they are being paid. They can use this information to figure out which position groups they want to allocate their budget to in the future.

Execute:
> Select teamLevel, position, SUM(salary) as totalSalary
From Players, Teams
Where Players.Teams_teamID = Teams.teamID
Group By teamLevel, position
Having SUM(salary) > 500000

+ -------------- + ------------- + ---------------- +
| teamLevel      | position      | totalSalary      |
+ -------------- + ------------- + ---------------- +
| League 1       | Forward       | 2050000          |
| League 1       | Midfielder    | 520000           |
| League 1       | Defender      | 510000           |
| League 2       | Forward       | 1300000          |
| League 2       | Midfielder    | 850000           |
| League 3       | Forward       | 1450000          |
| League 3       | Midfielder    | 790000           |
+ -------------- + ------------- + ---------------- +
7 rows



Query 2: Select all the kits for team 1

Justification: This query allows the club to see which kits are utilized by Team 1. This information could be used by the coaching staff to figure out which kits the team will wear for which matches.

Execute:
> Select kitName FROM Kits
Where Teams_teamID = 1

+ ------------ +
| kitName      |
+ ------------ +
| Home Kit     |
| Away Kit     |
| Goalkeeper Kit |
| Alternate Kit |
+ ------------ +
4 rows

Query 3: Find the names of players who suffered knee injuries:

Justification: This data could be used by the club’s training staff to see which players, and how many players, will need treatment for their knee injuries.

Execute:
> Select firstName, lastName
From Players, Injury
Where Players.PlayerID = Injury.Player_playerID
And injuryType IN ("Knee")

+ -------------- + ------------- +
| firstName      | lastName      |
+ -------------- + ------------- +
| Kevin          | De Bruyne     |
| Harry          | Kane          |
+ -------------- + ------------- +
2 rows

Query 4: Find the names and teamID’s of team staff members that have a job title of Marketing and have the last name Anderson:

Justification: We have an HR complaint for a person in the marketing department with the last name of Anderson 

Execute:
> Select staffFname, staffLname, teamID
From Team_Staff, Teams
Where Teams.teamID = Team_Staff.Teams_teamID 
And title IN ("Marketing")
And staffLname regexp "Anderson"

+ --------------- + --------------- + ----------- +
| staffFname      | staffLname      | teamID      |
+ --------------- + --------------- + ----------- +
| David           | Anderson        | 1           |     
+ --------------- + --------------- + ----------- +
1 row

Query 5: Find the names and salaries of defense coaches whose salaries are greater than the average salaries of the team staff members

Justification: Our Club would like to see if we are valuing our average defense coaches more than the average of all our coaches 

Execute:
> Select coachFname, coachLname, salary
From Coach
Where title regexp "Defense Coach"
And salary > 
	(Select AVG(salary) from Team_Staff)

+ --------------- + --------------- + ----------- +
| coachFname      | coachLname      | salary      |
+ --------------- + --------------- + ----------- +
| Patricia        | Hernandez       | 67000       |
+ --------------- + --------------- + ----------- +
1 rows

Query 6: Find the name and location of the stadium, as well as the date of the match, where a player suffered either an ankle or foot injury. Specify which type of injury was suffered.

Justification: This data will allow the club to see which fields may be more susceptible to ankle and foot injuries. This information is valuable because if there is a trend where a certain field sees more ankle and foot injuries than other fields, then they can work on improving the conditions of the pitch.

Execute:
> Select stadiumName, CONCAT(city, ", ", state) as location, matchDate, injuryType
From Stadium, Matches, Injury
Where Stadium.stadiumID = Matches.Stadium_stadiumID
And Matches.matchID = Injury.Matches_matchID
And injuryType regexp "Ankle|Foot"

+ ---------------- + ------------- + -------------- + --------------- +
| stadiumName      | location      | matchDate      | injuryType      |
+ ---------------- + ------------- + -------------- + --------------- +
| Puma Park        | Dallas, TX    | 2023-01-15     | Ankle           |
| Adidas Stadium   | Los Angeles, CA | 2023-01-08     | Foot            |
+ ---------------- + ------------- + -------------- + --------------- +
2 rows

Query 7: Lists all the players in the club that are from Brazil, this is for a simple 

Justification: The Brazilian national team has a series of games coming up and the team sees which players may potentially have to miss club games for international games. 

Execute:
> Select firstName, lastName, playerID, teamID
From Players, Teams
Where Players.Teams_teamID = Teams.teamID
And nationality REGEXP ("Brazil")

+ -------------- + ------------- + ------------- + ----------- +
| firstName      | lastName      | playerID      | teamID      |
+ -------------- + ------------- + ------------- + ----------- +
| Neymar         | da Silva Santos | 3             | 1           |
| Casemiro       | Santos        | 14            | 2           |
| Marcelo        | Vieira        | 17            | 2           |
| Thiago         | Silva         | 18            | 2           |
+ -------------- + ------------- + ------------- + ----------- +
4 rows

Query 8: Upper management wants to know which position has the highest average salary

Justification: This data could be used by the club’s front office to see which positions they spend the majority of their budget on, so that they can focus on trying to even out the distribution of the team’s budget should they so choose.

Execute:
> Select Position, avg(salary) as Average_Salary
From Players
Group by Position

+ ------------- + ------------------- +
| Position      | Average_Salary      |
+ ------------- + ------------------- +
| Forward       | 342857.14285714284  |
| Midfielder    | 270000              |
| Defender      | 238333.33333333334  |
| Goalkeeper    | 160000              |
+ ------------- + ------------------- +
4 rows

Query 9: Find the result of the games that england players have head injuries that are playing forward 

Justification: There is a new regulation in England on concussions for their athletes so we need to make sure that we are vigilantly keeping up to date about their head injuries 

Execute:
> Select result, injuryType, nationality, position 
from Players, Injury, Matches 
Where Injury.Matches_matchID = Matches.matchID 
And Players.playerID = Injury.Player_playerID
And nationality IN  ("Italy")
And injuryType IN ("head")
And position IN ("Goalkeeper")

+ ----------- + --------------- + ---------------- + ------------- +
| result      | injuryType      | nationality      | position      |
+ ----------- + --------------- + ---------------- + ------------- +
| Loss        | Head            | Italy            | Goalkeeper    |
+ ----------- + --------------- + ---------------- + ------------- +
1 rows

Query 10: Find the number of players grouped by nationality who salaries are above the average salaries of players 

Execute:
> Select nationality, COUNT(*) as Number_Of_Players from Players 
Group by nationality

+ ---------------- + ---------------------- +
| nationality      | Number_Of_Players      |
+ ---------------- + ---------------------- +
| Argentina        | 1                      |
| Portugal         | 1                      |
| Brazil           | 4                      |
| Belgium          | 3                      |
| Spain            | 1                      |
| France           | 3                      |
| Poland           | 1                      |
| Croatia          | 1                      |
| Netherlands      | 2                      |
| England          | 3                      |
| Germany          | 2                      |
| Italy            | 1                      |
| Norway           | 1                      |
| Senegal          | 2                      |
| Cuba             | 1                      |
| Uruguay          | 1                      |
| Morocco          | 1                      |
| USA              | 1                      |
| Botswana         | 1                      |
+ ---------------- + ---------------------- +
19 rows

## Database information

| Type | Query 1 | Query 2 | Query 3 | Query 4 | Query 5 | Query 6 | Query 7 | Query 8 | Query 9 | Query 10 |
|------|---------|---------|---------|---------|---------|---------|---------|---------|---------|----------|
| Multiple Table Join	|	| 	|	|	|	| X |	|	| X |	|
| Traditional Subquery	|	| 	|	|	| X |	|	|	|	|	|
| Correlated Subquery	|	| 	|	|	|	|	|	|	|	|	|
| Group By	|	| 	|	|	|	|	|	| X |	|	|
| Group By Having	| X | 	|	|	|	|	|	|	|	|	|
| Multi Condition Where	|	| 	| X | X |	| X |	|	| X |	|
| Built In Function	| X | 	|	|	| X |	|	| X |	|	|
| Reg Exp	|	| 	|	| X | X | X | X |	|	|	|
| Concat	|	| 	|	|	|	| X |	|	|	|	|

