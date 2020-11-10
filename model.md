## Notes ##

Size concerns:
1 season ~= 1GB
might want to batch train by season
create script that gets season-by-season data, cleans it, then saves to csv
Then train model with each batch

Historical betting lines at Vegas Insider?

Approach:
Get expected value for each pitch (velo, spin, sequencing?, handedness, situation?, fielding?)
(maybe include some proxy for pitcher command, maybe strike % in non-close games with no one on and 3-0? Does Fangraphs have the scouting command rankings for all pitchers?)

Use Bayesian something (what are the priors?) to get pitcher and hitter quality based on results above/below expectation
How can I get the model to update more quickly between seasons? (players change more in offseason, and I bet lines are off more in the beginning of the year)

Use player ratings to come up with team expectations

How to incorporate fielding into team projections? 