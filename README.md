# Beyond the Box Score: Possession Metrics and Success in the NHL

## Overview

This analysis focuses on two main areas:

1.	**How puck possession metrics such as Corsi For % (CF%) and Fenwick For % (FF%) correlate with team success in the NHL**. The visualizations explore both **season-level 	relationships** and **year-over-year momentum**, offering insight into how modern NHL front offices may value sustained puck control as a driver of performance.

2.	**League-wide trends in team composition, player salaries, and key drivers of team-building success.** While the On-Ice Strategies Dashboard explores the strategies coaches and players should implement during NHL hockey games, we also wanted to look into how general managers of NHL teams should think about crafting their teams in the first place. General managers are in charge of scouting players and extending contract offers to players, but there is no agreed-upon strategy for doing this. Providing an NHL general manager with clearly visualized data can help them make decisions about where to utilize their finite resources in a way that will ultimately set their players and coaches up for success. 



## Key Questions Addressed

1. Do teams with stronger puck possession metrics (CF%, FF%) accumulate more points and win more often?
2. How do possession gains year-over-year relate to actual on-ice performance improvements?
3. Can we identify the most efficient teams in converting possession into points?
4. Where should GMs look for new players?
5.How much money are high-scoring players worth to a team?
6. What does the market look like in terms of contract length?
7. At what age is it best for a team to sign players?
8. How crucial are different positions to team success?

## Summary of Visualizations - Puck Possession vs. Success

### Tableau Dashboard 1 - NHL Puck Possession Metrics vs. Season Success

**Features**:
- Interactive **scatter plot** (CF% or FF% vs. regular season points)
  - Filterable by season
  - Highlights playoff teams, Cup winners, and efficient teams
  - Dynamic parameter switching for possession metric between CF% and FF%
- Bar chart comparing **playoff vs. non-playoff average CF%/FF%**
- Custom summary panels for each selected season:
  - Stanley Cup winner and possession stats
  - Best CF% and FF% teams
  - Most efficient teams (points per possession)

**Design Elements Used**:
- Color theory: green/red playoff status, consistent blue-gray palette
- Gestalt layout: grouped stat panels, divider lines
- Typeface: Segoe UI for visual clarity
- Tableau functionality: LOD calcs, dynamic fields, image sheet joins, parameter-driven metrics

##### *See "NHL Possesions v Success Dashboard" packaged Tableau Workbook within project files
##### *See "NHL Possession v Success Dashboard - Video Walkthrough" within project files

#### Data Sources and Cleaning

The dataset required multiple levels of cleaning, enrichment, and normalization to ensure accurate visualizations across seasons:

- **Playoff team status** and **Stanley Cup winners** were **manually entered** by season, based on historical NHL results
- **Seasons prior to 2007–08** were excluded due to missing possession metrics (CF%, FF%)
- **Team rows were re-sorted alphabetically by team abbreviation** to allow correct YoY comparisons and match external data joins
- **Franchise changes** were accounted for:
  - Teams that **relocated** (e.g., Atlanta Thrashers → Winnipeg Jets) were normalized by abbreviation
  - **Expansion teams** were integrated by ensuring consistent naming across seasons
- Numeric formatting was standardized (e.g., CF% converted from strings to decimals)

##### *See "NHL Analytics Datasource" within project files for cleaned data
##### *See "sportsref_download" and "Moneypuck data pull" within project files for raw data

### Excel Chart 1 - YoY Change in CF% vs. Change in Points

**Chart**: YoY Change in CF% vs. Change in Points  
- Shows how well teams convert possession improvements into better results  
- Color-coded by playoff status  
- Quadrant analysis highlights divergent outcomes (e.g., improved possession but worse results)  
- Used Excel formulas to calculate deltas and grouped points using IF logic

#### *See "Excel Chart - Change in CF v Change in Points" in project files


### Design Principles Applied

- **Color Theory**: green/red for playoff status; diverging color scale dropped for clarity
- **Layout**: groupings leverage visual proximity, consistent alignment
- **Dynamic Visuals**: parameter-controlled y-axis, seasonal context updates
- **Typography**: clean and consistent; chart titles match X→Y convention

### Limitations
- Efficiency metrics like points per CF% are novel, not commonly used in mainstream hockey analysis
- CF% naturally trends toward 50% over time league-wide, limiting season-level comparative insights
- External factors (e.g., injuries, schedule, goalie performance) are not modeled

### Future Explorations
With more time, we would explore:
- Integrating expected goals (xG) or shot quality metrics
- Visualizing playoff round progression by possession tier
- Adding animation across seasons to show possession “momentum”



### Use of ChatGPT

ChatGPT was used as a:
- Tableau formula assistant (for LODs, dynamic labels, parameter set-up)
- Visual design consultant (suggestions for layout, color cohesion, caption structure)
- Technical assistant (debugging Tableau errors and Excel scatter plot logic)
- Project planner/tracker (assist in ensuring all required components are included and correctly formatted)

**Tableau Dashboard 2 - NHL Team General Manager Dashboard**

## Summary of Visualizations
**Player Age Trends of Top Scorers**
•	Built a dual-axis ribbon chart in Tableau showing the average, minimum, and maximum ages of top 10 scorers for each of the 2005–2024 NHL seasons.
•	Helps evaluate whether scoring dominance is shifting to younger players or older players. Are older players with more experience likely to be a top scorer? Or are younger players with better athleticism more likely to be a top scorer? 
•	Data: We directly exported and combined data from HockeyReference.com on the top 10 scorers from the past 20 seasons. This required minimal data cleaning, but we did have to calculate average age, minimum age, and maximum age on our own in excel.
•	Takeaways: Our chart shows that the average age of a top scorer has remained fairly consistent over the last 20 seasons, but there seems to be a clear trend of the minimum age of a top 10 scorer increasing in the last 20 years. Gone are the days of 18- and 19-year-olds coming into the league and immediately asserting themselves as top players. This suggests that NHL GMs should prioritize allocating more of their resources towards players who are closer to their prime (~28 years old) instead of investing in larger contracts for younger players.

**2. Player Nationality Trends**
•	Created a stacked area chart in Tableau to show changing distribution of nationalities from the past 20 NHL seasons.
•	This shows where other NHL GMs are finding their players, and would help a GM know which countries they should prioritize in their scouting efforts. 
•	Data: We initially tried to use Python to scrape nationality data from QuantHockey.com, but this was NOT successful, so we ended up copying and pasting the data directly from the website. We then had to clean the data in excel (this took a long, long time), filter the data to highlight countries with >1% player share, and ensure that country names were consistent across all years.
•	Takeaways: This chart shows that Canada is still the best place to look for new hockey talent, but that Europe and the US have been slowly increasing their shares of NHL players over the years. This suggests that the hockey landscape is changing as the sport becomes more international, and suggests that NHL GMs should probably be shifting more of their scouting resources towards Europe and the US to capture more of the emerging talent in these areas. In particular, Sweden and Russia seem to be producing more and more hockey talent, a takeaway that backs up our anecdotal experiences watching NHL hockey in recent years—very good to know!

**3. Goalie Performance vs. Team Success**
•	Developed a scatterplot (SV% vs Team PTS) for starting goalies from 2019–2024.
•	This chart answers the question of whether or not elite goaltending is necessary for team success. Is it important to pursue a top-end goalie? Or is the talent of a team’s goaltender largely irrelevant to overall team success? Are teams better off pursuing top-end skaters instead of top-end goaltenders?
•	Data: Exported goalie and team stats from HockeyReference.com and used Excel to merge these two datasets into one combined dataset to compare the relationship. This took some creative cleaning in excel, because individual goalie stats are largely skewed by small sample sizes and assigning a goalie to the correct team in the correct season was tricky. We had to write some fancy excel formulas to properly assign goalies to the correct teams in a correct season and then filtered out goalies who started less than half of their team’s games to ensure no sample size bias.
•	Takeaways: This scatterplot pretty convincingly shows a strong relationship between goalie skill and team success. In general, goalies with a higher Save Percentage (shots saved vs total shots) is correlated with higher team success (PTS are accrued with team victories and are how playoff spots are awarded in the NHL). If I were an NHL GM, this chart would tell me that I should absolutely be pursuing elite goalies due to their perceived outsized impact on team success.

**4. Contract Value vs Scoring Output**
•	Plotted AAV/Cap% vs PPG for top 100 contracts in each of the 2020–2024 NHL seasons in Tableau. AAV stands for Average Annualized Value of a contract (how NHL contracts are normally valued on a yearly basis), and PPG stands for Points Per Game, a measure of how effective individual players were in a given season.
•	This chart tells us whether there is a relationship between large contracts (normalized to the percentage of the NHL salary cap in a given year) and individual player scoring. This answers the question or whether handing out large contracts to star players usually yields higher-scoring seasons from those players, and whether or not it’s possibly to get elite scoring seasons from players under smaller contracts. In other words, how prudent is it to hand out mega-deals to top players?
•	Data: Again, we unsuccessfully tried initially to use Python to scrape this data from PuckPedia.com, but eventually had to resort to copying the data directly from the tables on the website. Fortunately, the website has the option to filter for specific metrics and years, which made things a little easier, but there was a fair amount of cleaning in excel for this one as well. We had to run our own calculations to determine player salaries as a percentage of the salary cap in a given year.
•	Takeaways: Even with the presence of individual player seasons where the player was injured and did not score a single point, there is a clear relationship between contract size and performance. Almost all elite seasons were had by players with larger contracts, and almost every top-end contract in this dataset yielded a season of elite scoring. This suggests to NHL GMs that handing out mega-contracts to star players pays off—don’t skimp out on signing your best players! This trend also seems to hold for all player positions (you can filter by position to see for yourself).

**5. AAV/Cap% by Signing Age**
•	Grouped bar chart showing how cap allocation varies by player signing age. Cap allocation is given by a player’s contract AAV divided by the NHL salary cap for that year—in other words, what percentage of a team’s total resources were given to that particular player. Signing age is the age at which the player inked their deal.
•	This chart tells us at what age players are able to command the highest contracts. From a team-building perspective, this tells a GM when the market values certain players more or less. 

•	Data: We again used data copied directly from PuckPedia.com after our failed Python attempt. While most of this data had already been cleaned for use in our earlier charts, we had to go one step further here in order to ensure no duplicate contracts were shown in this sample. To do this, we had to assign each contract its own unique key, and then filter by key to ensure no duplicates. 
•	Takeaways: There is a clear upwards trend in how much money players earn up until about their age 28 seasons, after which overall contract size drops off considerably. This suggests to GMs that it may be worth it to sign your younger players to longer, lower AAV contracts early on, as the longer you wait to sign your star players, the more money they can command on the open market. This also suggest that the league does not value players past their prime age of 28 nearly as much as they value the potential of younger players. All of this information is extremely useful to GMs as they try to decide how to allocate their resources for both current and future seasons. 

**6. Contract Length vs Signing Age (Contract Length vs Sign Age sheet in the DataVis_GM Dashboard All Raw Data excel file)**
•	Created in Excel for extra credit; deduplicated contract dataset to visualize whether younger players are receiving longer deals.
•	This chart can help GMs understand how early they need to begin thinking about giving out long-term contracts, and how far into a player’s career teams are generally willing to commit to. 
•	Data: This data was the same dataset as the AAV/Cap% by Signing Age chart (Chart 5), so no further data cleaning was required.
•	Takeaways: NHL GMs seem to be reluctant to hand out overly long contracts to players until they reach their age 22-23 seasons, and ages 22-26 seem to be the prime years for a player to receive a very long-term contract. NHL GMs seem to be willing to provide long-term deals to top players until around their age-30 seasons, after which contract length falls off. This chart also shows that, aside from a few notably outliers, 8 seasons seems to be a generally agreed upon maximum contract length. This information is very valuable to a GM who is entering into contract negotiations with a player. Knowing how long of a contract a player is likely to be able to command on the open market can help the GM land on the right contract length. 

**Assumptions & Limitations**
•	Goaltender impact is measured solely using SV%, which doesn’t fully capture rebound control or quality of shot faced, although our large sample size likely diminishes this impact. 
•	Contract data is limited to the top 100 AAV contracts per season, skewing the analysis toward higher-performing players.
•	Some nationality percentages are approximate due to rounding or exclusion of players under the 1% threshold.
•	Data on defensemen and role players is underrepresented in the current scorer-based trends.


**Relevance to NHL GMs**
These dashboards were designed with NHL executives and analysts in mind:
•	Age and nationality trends support scouting and development strategy.
•	Goaltending efficiency vs. team success can influence budget allocation in roster planning.
•	Contract value and term charts help benchmark fair market rates and project future contract risk by player archetype.

**Additional Analysis With More Time**
•	Given more time or access to broader datasets, I would have explored:
•	Full salary cap usage by team and positional breakdowns
•	Injuries and games missed vs. contract efficiency
•	War-on-ice-style metrics for adjusting cap value relative to advanced performance data (e.g., xG, zone entries)
•	Impact of high-scoring players vs. effective defense players on team success, and contract sizes for different types of players (defensive specialists, powerplay specialists, backup goalies, etc.)

**Use of ChatGPT**
ChatGPT was used throughout the project to:
•	Suggest visualization types aligned to audience goals
•	Recommend Excel cleaning workflows and Tableau formulas
•	Provide structure and phrasing for this write-up and general documentation
•	All decisions were reviewed and applied by me with full understanding of the underlying data.




