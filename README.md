
# Business Formation Statistics by State

[Final Visualization](https://justinkraus.github.io/BFS/)

I was attracted to the business formation statistics (BFS) dataset as I’m interested in exploring alternative methodologies that measure where jobs are growing in the US. The BFS data is an experimental measure for measuring economic activity, meaning its not a formal measurement that guides Federal monetary policy, but is something that is being considered and refined for future use. 

## Iteration 1

1.  Acquired data from census site: [https://www.census.gov/econ/bfs/index.html](https://www.census.gov/econ/bfs/index.html)
    
2.  At the link above you'll find Tableau dashboards that capture short time periods of BFS data. However I set-out to measure aggregated business application for the entire time period available to determine which states have had the most business applications since 2006.
    
3.  Merged data at the state-level with a state shape file to to create a choropleth map in kepler: [https://alicia.data.socrata.com/Government/States-21basic/jhnu-yfrj](https://alicia.data.socrata.com/Government/States-21basic/jhnu-yfrj),
    

  

![](https://lh4.googleusercontent.com/bmKoRPQxduND5YZhJgahqa6s45sXN2JohH4mb_PT5qHgNR0XKNWD-_ttkdiJHMtwg8U7c78SDnz-5MzZpUKY4cpeKmPTVpxUeYKEz6mkWnNeKdSXA8MgMHb4XYMIT8NwFBZHWWhV)

All corporate business applications from 2006-present, darker purple indicates more activity

As much as [I like using Kepler](https://github.com/justinkraus/Cartography), I realized a lot of the functionality that had attracted me to Kepler in the past (interactivity and high granularity) was unnecessary for a state-level choropleth.

## Iteration 2
In the initial dataset, three types of business formation statistics are provided. I refocused the visual to observe only on "high-propensity business applications" which the census bureau believes will likely translate into a wage paying job as opposed to more general business activities. Additionally I added a column filter that separates items into two time intervals: 2006-October 2020 and March-October 2020 to observe if there had been any material impacts from the lockdown measures on new business applications by state. 

Additionally I decided to use d3.js for this update as per the reasons mentioned in the previous section:

 - The [current script](https://github.com/justinkraus/BFS/blob/master/index.html) loads a csv of the business applications for each time period
 - Merges them to a [JSON file containing the states shapes](https://github.com/justinkraus/BFS/blob/master/us-states.json)
 - Colors states by number of business applications.

![](https://lh3.googleusercontent.com/AqRpGVhqmnS0CzelEs9IeYer3zIV1PHaj11ud7mEZ70Wqm7wa4lbdcgdU28a9sAEuAlUfA16kHnW-6PTfavnYHe87T0cGudAq6PBL7gCQ9c-cnx3-N-BmFyW7T3NeXEwdH6NxFOw)