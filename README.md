# Beyond the Box Score: Possession Metrics and Success in the NHL

## Overview

This analysis focuses on two main areas:

1.	**How puck possession metrics such as Corsi For % (CF%) and Fenwick For % (FF%) correlate with team success in the NHL**. The visualizations explore both **season-level 	relationships** and **year-over-year momentum**, offering insight into how modern NHL front offices may value sustained puck control as a driver of performance.

2.	**JAKE INPUT SOMETHING HERE**



## Key Questions Addressed

1. Do teams with stronger puck possession metrics (CF%, FF%) accumulate more points and win more often?
2. How do possession gains year-over-year relate to actual on-ice performance improvements?
3. Can we identify the most efficient teams in converting possession into points?
4. **JAKE INPUT SOMETHING HERE**
5. **JAKE INPUT SOMETHING HERE**
6. **JAKE INPUT SOMETHING HERE**

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

## Summary of Visualizations - XXXXXXXXXXXXXXXXXXXXX
**JAKE INPUT SOMETHING HERE**

**JAKE INPUT SOMETHING HERE**

**JAKE INPUT SOMETHING HERE**

**JAKE INPUT SOMETHING HERE**

**JAKE INPUT SOMETHING HERE**

**JAKE INPUT SOMETHING HERE**

**JAKE INPUT SOMETHING HERE**



