# Notes #

## Size concerns:
1 season ~= 1GB
might want to batch train by season
create script that gets season-by-season data, cleans it, then saves to csv
Then train model with each batch

Historical betting lines at Vegas Insider?

## Pitch model: 
Get expected value for each pitch (hp_umpire?, velo, spin, sequencing?, handedness, situation?, fielding?, swing%, contact%, xwRC+, count, likelihood of strike call)
Need xwRC+ by count (I think I can create this without too much trouble)
might need to create custom relative metrics for each pitcher (88mph changeup is different for a guy who throws a 90mph fastball vs. 98mph)
 - Maybe just difference from fastball? Difference from avg. pitch?
 - Bucket ranges of stats, so you have everything from last month as seperate variables from everything 2 months ago (or whatever)
 - (maybe include some proxy for pitcher command, maybe strike % in non-close games with no one on and 3-0? Does Fangraphs have the scouting command rankings for all pitchers?)
 - wOBA not park adjusted (should be pretty easy to create custom park factors?)
   - Can create xwRC+ (forumula/totorial here: https://library.fangraphs.com/offense/wrc/)
   - (https://www.bleedcubbieblue.com/2012/10/30/3567746/sabermetrics-101-wrc) gives following formulas converting wOBA to wRC+
        - wRC = [((wOBA - lgwOBA)/wOBAScale) + (lgR/PA)] * PA
        - wRC+ = 100 * (wRC/lgwRC)
- Might not matter for predicting winners, but temperature will likely be important for over/unders (might be tricky to seperate from park effects)

_Defense_
- ignore at this level because the outcome I'm predicting is xwRC+ based on exit velo / launch angle, def already stripped out


## Player model:
Use Bayesian something (what are the priors?) to get pitcher and hitter quality based on results above/below expectation
How can I get the model to update more quickly between seasons? (players change more in offseason, and I bet lines are off more in the beginning of the year)

Add in defense and baserunning 
Catcher framing?

## Game model:
Use player ratings to come up with team expectations
How to incorporate fielding into team projections? (probably at player level)
Add in bullpen rest situation (could also incorporate this at player level with talent decreasing if they've been used a lot recently)

_Nice to haves_
- Interaction effects w/ eg. gb pitchers and good IF defense
- Interaction effects w/ battery and baserunners 