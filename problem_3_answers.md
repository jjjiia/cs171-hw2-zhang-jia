1. 
The ideal graph would include details of each commit, which files were changed within the repo would be a nice addtion to just the branches in general. A network graph could also adress clustering of authors who work on certain features, which lets users of the repo identify who to ask help from, this may be a different topology than the current network based on commits. 
Another important thing is to show overview of the network which allows highlevel comparisons such as between repos and change over time.

2. 
jquery has a very large number of active contributors, there are not many branches in comparison to the other 2. 
bootstrap has few but very substantial contributors, d3 is somewhere in the middle. Bootstrap has more frequent commits, based on the 100 recent commits I fetched, d3 has 100 over 3 months, while the last 100 commits for jquery was occur in about 8 months, for bootstrap, it is only 1 month or so. 

3. 
force directed graph is not impacted, because it had very little clarity in terms of data at first glance, i think it is actually stronger with more nodes because patterns could potentially emerge.

For the time scale, because i had built the whole visualization using d3 data, it didn't work well for the other repos and shows the need for the date scale/axis to be dynamic. 

4. 
This is a wish list in the order of how I will create the features: 

for the author/time layout - 
Dynamic placement of authors - so that it always fits the contributors on the page, because there is not reason to scroll down that much.
Dynamic timescale - the width maps to about 10% of the the entire timeline of the repo so that there is not as much scrolling as the current github network graph
Adjustable timescale - to zoom in and out for the timescale, so that a overview can be achieved.
A input box for the repo name so that maybe others will be able to use it.

for the force directed -
A network graph on the file level rather than commit level so that the two can be compared and contrasted.
A friend showed me git blame feature, which is essentially the most zoomed in detailed data, it shows the changes line by line. So it would be great to work with branch network, file network, and git blame as 3 scales at which to view the network. 

overall - 
i like to get rid of some of the visual elements from the current github graph so that it is more economical and also looks nicer.

As I revisit my plans from last week on thursday morning, i realize not all these will be done. 