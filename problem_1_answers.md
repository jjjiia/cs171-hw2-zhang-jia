CONTRIBUTORS
Audience: project manager and contributors can see overview of project's active vs. inactive periods of development, as well as own commits in relation to collaborators' commits. Visitors can get a quick sense of the main contributors to the repository and its history.

Data: The data being used are contributor, number of commits(pluses and minuses), the date of each action. All contributor data are aggregated in the top graph to provide an overview of project history.

Getting Data: A overview of the repo can be gotten here: https://api.github.com/repos/mbostock/d3, View the first page of commits for all contributors at: https://api.github.com/repos/mbostock/d3/commits, and use pagination to iterate through the pages by making a for loop where i is the page number and the string is constructed as: "https://api.github.com/repos/mbostock/d3/commits?page="+i+"&per_page=100"  where there are 100 entries per page, and max i is the total number of commits in repo divided by the number of entries per page.

What happens: 
If a person make many commits, their histogram of activities would rise to the top, under the overall activities, and their contributions would be reflected in the large graph on top of the page as well. 



COMMITS ACTIVITY
Audience: This can be for a project manager to see the progress of the repo, and also for a user to quickly gage if the repo is still active, if it is in decline or just being sporatically built. It has 2 views, for the past 1 year, and each week that year. It is navigable by the left and the right key where each bar represents a week, and when a bar is highlighted, the activity of each day of that week are shown. 

Data: The data being used are dates, and number of commits for the past year. They are represented 2 ways, as a condensed timeline, and a detailed version for a week one at a time.

Getting Data: this data can be found in the commit activity of stats, using this command to save the dat to a json file: curl "https://api.github.com/repos/mbostock/d3/stats/commit_activity" -o commit_activity.json
the format starts on a Sunday.

What Happens:
With a lot of commits? The bottom graph's smallest unit is a day, it actually takes a lot of screen size for the simple line graph, if the data is time stamped anyways, it might be helpful to add the time of commits to make the graph more detailed. The graph would be better this way especially if the nodes of the bottom graph links to a list of commits that day, hour, or 2 hour period.



CODE FREQUENCY
Audience: This could be for the project manager and contributors, although it is not interactive so it is difficult to see what the additions and deletions are.

Data: weekly additions and deletions to the cod base, for the entirty of the repo's history.

Getting Data: this was similar to above, curl "https://api.github.com/repos/mbostock/d3/stats/code_frequency" -o code_frequency.json

What Happens: The scale of this graph is quiet large, in the 40k range for the d3 repo, so there isn't a high resolution, I imagine large changes are reflected, but not as dramatically as in other graphs. It would be nice to have both on the positive y axis, so you can see the difference more clearly - at what rate are additions being accumulated?



PUNCH CARD
Audience: This is useful for a individual user to see his or her own habits in commiting, or for a repo the community's habits. It looks like d3 starts its day between 8-9am, and is especially productive on wednesdays. This could reflect the habits of the 2 main contributors.

Data: day of week, hour of day, number of commits each hour

Getting Data:  curl "https://api.github.com/repos/mbostock/d3/stats/punch_card" -o punch_card.json

What Happens: the graph would scale so that contributions at other times seem very small in comparison to a lot of commits in a short period of time. I think this graph is really useful.



PULSE
Audience: Primarily for project manager to see overview of the current status of the repo.

Data: Pull requests, issues, contributors and commits in the last week and the associated files links in list form. 

Getting Data: for issues: curl "https://api.github.com/repos/mbostock/d3/issues" -o issues.json will show you the issue's title, the contributor, the staus on open and closed issues.

What Happens: I think this graph because it is more text based, it is for reading rather then at a glance, so the format will scale for a large number of commits because there is little graphic change. 



GITHUB NETWORK GRAPH
Audience: for the project manager this is important to see both the structure of collaboration, and also track changes.

Data: the data is merges, pushes, and pulls over time. 

Getting Data: 
forks: https://api.github.com/repos/mbostock/d3/forks 
pulls: "https://api.github.com/repos/mbostock/d3/pulls"

What Happens: a great number of commits does not change the network graph a lot, unless the work is pulled and merged. it would be less legible with more data. I am not sure if a more organic layout would make this 

Role of Interaction: the interaction is important here to see what the intersections mean, what issues were fixed by a merge, or 

New Developers: because the graph scrolls down to different users, it would be harder to see the extent to which new developers have used the repo once they have forked it, however, based on the branching of the top main user, you can see patterns where many forks are made at the same time. 