# FIFA Replacement Strategy
This project's goal is to recommend replacement players to the Real Madrid Football Club.

## goal
The client for this project is a fictional recruiting manager of the Real Madrid Football Club. This manager has the job of recruiting new players to the club. His goal is to improve the skill of the club as much as possible, within certain parameters. For this project, the manager wants help recruiting new players who are already playing in fifa clubs. 

## parameters
* recruiting pool: existing fifa players
* replacement pool: current Real Madrid players
* budget: replacement players cannot cost more then the players they are replacing
    * for the sake of simplicity, I do not take into account contracts. I assume the timing of hiring is not an issue.
* optimization parameter: the aggregate Overall ratings of players
    * 'Overall' is a feature of the data that designates an individual player's overall skill
   
## solution
There are 1 layers of analysis that can be applied to recommend replacement players. 

1. **Simple Filter:** a filter that takes into account wage, position, and overall rating to make recommendations based on the input of replacing a single specific player. This filter takes into account that younger players will get a higher overall rating as they get older, by adjusting the overall rating by age.

## project layout
0. brainstorm solutions feature by feature
1. [Clean the data](clean.ipynb)
2. [Create filter on wage, position, and overall rating](filter_simple.ipynb)
3. [Add age adjusted overall rating to filter](filter_age_adjusted.ipynb)
4. [Wrap the solution in a function](scale_solution.ipynb)

## secondary explorations 
The following explorations do not directly suggest recommendations, however they give insight that speaks to understanding a player's skills.
[Predict overall rating based on individual techniques](predict_performance.ipynb)
[Determine whether a player is a specialist or a generalist](rating_distribution.ipynb)
[Explore the relationship between preferred and best positions](preferred_positions.ipynb)

## installation guide
```
git clone https://github.com/ncernek/fifa_replacements.git
cd fifa_replacements/
pip install -r requirements.txt
```

## source
This data comes from [kaggle.com](https://www.kaggle.com/thec03u5/fifa-18-demo-player-dataset).
It contains:
* Player personal attributes (Nationality, Club, Photo, Age, Value etc.)
* Player performance attributes (Overall, Potential, Aggression, Agility etc.)
* Player preferred position and ratings at all positions.

Note that it does not contain any game data, such as points scored, or any club data,
such as numbers of wins.
