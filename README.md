# College_basketball_analysis
___
## Project Overview <br>
<br>
The NCAA Tournament, March Madness, so many peoples favorite time of the year, basketball, passion, heart, upsets, all of it is on display to the fullest for 3-4 weeks every year (except 2020 sadly). I am not much of a college basketball enthusiast in general, I have always enjoyed the NBA more, but I cant help but get pulled into March Madness every single year. Never has something been more aptly named because thats what it is, madness. And anyone who has ever made a bracket knows this. Since the field opened to 64 teams noone has ever even gotten close to having a perfect bracket. The closest ever was 44 straight correct predictions. The chances of a perfect bracket are 1 in 9.2 quintillion, a little better if you are someone who watches college basketball of course. But my goal is not to get a perfect bracket by any means but instead just to try an get a better idea of what stats correlate to teams doing well or doing poorly during the tournament.

The idea of this project is just to try and analyze data on previous NCAA tournaments to see if I can find any similarities or data that can help provide insight on the current NCAA tournament. This is just a fun little side project that I hope I can use in the future to help with my March Madness Brackets.
<br>
<br>
The first analysis method was to take a look at the statistical cases for all these teams by comparing them to teams from 2013-2019 who have made the tournament. This included comparing the current teams individually to all other teams as well as comparing them to the average stat of each postseason finish for each team.
<br>
<br>
The second method of analysis was to generate a predictive model. Using the data from the years 2013-2019 as a training set, I created an XGBoost model as it gave me the best class balance needed for the prediction. In this prediction the model showed Gonzaga as the favorite to win the championship.
<br>
<br>
The next step is now to take that model and the features I am currently using and refine them. Whether it be limiting the features in the model to only the most valuable using feature importance. Or tuning the hyper parameters of different models to find the one that gives the absolute best overall prediction. 
<br>
<br>
Finally after these steps the last goal will be to gather the data on the current NCAA tournament results now that the tournament has been completed and see how the final model did by comparison. 
___

## Data <br>
<br>
The data I used is from a kaggle dataset, College Basketball Dataset by Andrew Sundberg. <br>
<br>

## Notebook Data <br>
<br>

- **Gathering Specific Data:** <br>
    - Basic overview of the general data obtained from the kaggle dataset.<br>
    - Just a look at the data there as well as some removal of very unnecessary data.
- **Data_Cleaning:** <br>
    - Cleaning up data further, this time focusing on 3 sets of data (the cbb_21 with the 2021 season data, the cbb general with all the teams from 2013-2019 that made the tournament, and a new cbb_avg that i made with all the data from the 2013-2019 season averaged by post season finish). <br>
    - Using those 3 to make sure all the columns had the same name, and they all had the same statistics available
- **Similarity_Matrix:** <br>
    - Used to run multiple Matrices to compare the 2021 teams to past teams and general team performance by their postseason finish. <br>
    - This is used to then generate CSV files with data on the similarity between the teams to be visualized later.
- **Modeling:** <br>
    - Generated a base model using xgboost model to get an idea of how well the model works. <br>
    - Will need to do better to take into account the large disparity on the amount of teams who lose in the first round and make the final.
    - Used the base model to gather predictions for the current NCAA Tournament
<br>

- **SQL Files:** <br>
    - Put all sql database files into a folder to keep the overall cleaner look
- **CSV Files:** <br>
    - All stored in a separate folder to keep the overall look clean
- **Visualizations:** <br>
    - All visuals created from the data using Tableau to provide the visualizations with a cleaner Look. <br>
    - Also added the tableau workbook for people to be able to go in and look at more specific things as well
___

### Variables <br>
<br>
RK (Only in cbb20): The ranking of the team at the end of the regular season according to barttorvik

TEAM: The Division I college basketball school

CONF: The Athletic Conference in which the school participates in (A10 = Atlantic 10, ACC = Atlantic Coast Conference, AE = America East, Amer = American, ASun = ASUN, B10 = Big Ten, B12 = Big 12, BE = Big East, BSky = Big Sky, BSth = Big South, BW = Big West, CAA = Colonial Athletic Association, CUSA = Conference USA, Horz = Horizon League, Ivy = Ivy League, MAAC = Metro Atlantic Athletic Conference, MAC = Mid-American Conference, MEAC = Mid-Eastern Athletic Conference, MVC = Missouri Valley Conference, MWC = Mountain West, NEC = Northeast Conference, OVC = Ohio Valley Conference, P12 = Pac-12, Pat = Patriot League, SB = Sun Belt, SC = Southern Conference, SEC = South Eastern Conference, Slnd = Southland Conference, Sum = Summit League, SWAC = Southwestern Athletic Conference, WAC = Western Athletic Conference, WCC = West Coast Conference)

G: Number of games played

W: Number of games won

ADJOE: Adjusted Offensive Efficiency (An estimate of the offensive efficiency (points scored per 100 possessions) a team would have against the average Division I defense)

ADJDE: Adjusted Defensive Efficiency (An estimate of the defensive efficiency (points allowed per 100 possessions) a team would have against the average Division I offense)

BARTHAG: Power Rating (Chance of beating an average Division I team)

EFG_O: Effective Field Goal Percentage Shot

EFG_D: Effective Field Goal Percentage Allowed

TOR: Turnover Percentage Allowed (Turnover Rate)

TORD: Turnover Percentage Committed (Steal Rate)

ORB: Offensive Rebound Rate

DRB: Offensive Rebound Rate Allowed

FTR : Free Throw Rate (How often the given team shoots Free Throws)

FTRD: Free Throw Rate Allowed

2P_O: Two-Point Shooting Percentage

2P_D: Two-Point Shooting Percentage Allowed

3P_O: Three-Point Shooting Percentage

3P_D: Three-Point Shooting Percentage Allowed

ADJ_T: Adjusted Tempo (An estimate of the tempo (possessions per 40 minutes) a team would have against the team that wants to play at an average Division I tempo)

WAB: Wins Above Bubble (The bubble refers to the cut off between making the NCAA March Madness Tournament and not making it)

POSTSEASON: Round where the given team was eliminated or where their season ended (R68 = First Four, R64 = Round of 64, R32 = Round of 32, S16 = Sweet Sixteen, E8 = Elite Eight, F4 = Final Four, 2ND = Runner-up, Champion = Winner of the NCAA March Madness Tournament for that given year)

SEED: Seed in the NCAA March Madness Tournament

YEAR: Season
___
### Medium Article

- Part 1: https://antoniohila.medium.com/march-madness-analysis-pt-1-5ce72fb9f0df
- Part 2: https://antoniohila.medium.com/march-madness-analysis-part-2-57adcff3d0c4
- Part 3: https://antoniohila.medium.com/march-madness-analysis-part-3-798645b1ee38

