# ICC Men's T20-Cricket World Cup 2022 Data Analytics


## Problem Statement :

In this project, I created a Power BI dashboard to review and compare the performances of all players in the T20 Men's Cricket World Cup 2022. The dashboard also helps in selecting the best 11 players of the tournament based on specific performance criteria given in the problem statement.

## Datasource :

The dataset used in this project was sourced from the Codebasics YouTube channel, which provided well-structured data on match statistics, player performances, and overall tournament insights for the T20 Men's Cricket World Cup 2022.

## Data Collection:

As the dataset was pre-collected and readily available, web scraping was not required. The data was processed and refined using Jupyter Notebook to ensure consistency and accuracy before conducting further analysis in Power BI.


## Data Transformation:
Performed initial data cleaning after scrapping such as player name correction, handle missing value, match id linking etc. using Pandas. Transformed the final data for dashboard using Power Query of Power BI.

## Data Modelling:
Connected all the datasets with based on some defined primary keys such as team and match ids. Also, created many measures, calculated columns and parameters for data analysis and dash boarding using DAX.

## Data Analysis Expression (DAX)
Measures used in visualization are:

- Total Runs = `SUM(t20_batting_summary[runs])`

- Total Innings Batted =`COUNT(t20_batting_summary[matchID])`

- Total Innings Dismissed = `SUM(t20_batting_summary[Out])`

- Batting Avg = `DIVIDE([Total Runs],[Total Innings Dismissed],0)`

- Total balls faced =`SUM(t20_batting_summary[balls])`

- Strike rate = `DIVIDE([Total Runs],[total balls faced],0)*100`

- Batting Possition = `ROUNDUP(AVERAGE(t20_batting_summary[battingPos]),0)`

- Boundary % = `DIVIDE(SUM(t20_batting_summary[Boundary runs]),[Total Runs],0)*100`

- Avg. balls faced = ` AVERAGE(t20_batting_summary[balls])`

- wickets = `SUM(t20_bowling_summary[wickets])`

- - Balls Bowled = `SUM(t20_bowling_summary[balls])`

- Runs Conced = `SUM(t20_bowling_summary[runs])`

- Economy = `DIVIDE([Runs Conced],([Balls Bowled]/6),0)`

- Bowling Strike Rate =`DIVIDE([Balls Bowled],[wickets],0)`

- Bowling Avrage = `DIVIDE([Runs Conced],[wickets],0)`

- Total Innings Bowled = `DISTINCTCOUNT(t20_bowling_summary[matchID])`

- Dot Ball % =` DIVIDE(SUM(t20_bowling_summary[zeros]),SUM(t20_bowling_summary[balls]),0)`

- Player selection = `if(ISFILTERED(t20_players_info[name]),"1","0")`

- Display Text = `if([Player selection] = "1"," ","Select Player(s) by clicking the player's name to see their invidual or combined strength")`

- - Color Callout Value =`if([Player selection]="0","#E8D166","#1D1D2E")`

- boundary runs batting =`t20_batting_summary[fours]*4 + t20_batting_summary[sixes]*6`

- boundary runs bowling =`t20_bowling_summary[fours]*4+t20_bowling_summary[sixes]*6`

- ## Reports:
Data visualization for the dataset was done using Microsoft Power BI Desktop:
