# Kickstarting with Excel

## Overview of Project
The client Louise needs to obtain at least $10,000 of funding to launch her play "Fever" and has decided to seek the capital through a crowdfunding initiative.  She has asked us to help identify attributes of historically successful campaigns and provide her recommendations on how to structure her crowdfunding to increase the likelihood of it being a success.

### Purpose:
- Use data on the success and failure of historical crowdfunding initiatives to provide analysis of outcomes based on their attributes
- Provide Louise recommendations on how to structure her initiative to increase likelihood of success
- Identify gaps with current dataset and other visualizations or analysis that might provide additional insights

## Analysis and Challenges
There are a number of decisions Louise needs to make regarding the nature of the crowdfunding, including, but not limited to:
- *Time of year to launch the initiative*: does launching at a specific time mean the project is lost in a large volume of similar requests vs. launch at a time of year when supporters aren't as motivated to give?
- *Target funding goal*: does Louise ask for an amount that is achievable but that might not cover all costs vs. ask for more than what she might need (contingency funds) but potentially dissuade backers from donating to a project that seems unachievable?
- *Target geography*: where should Louise seek funding, based on a country's taste in the content of plays in general, to garner more financial support?
- *Title and description*: can Louise change how she markets the play in order to attract more backers?

Decision #3 is not a feasible option if Louise is unable to travel in order to launch her play.  And while she can modify the marketing content of the play in the crowdfunding page, it would require more advanced analytical techniques (text mining) and the data might be too dissimilar to provide any actionable insights.  Decisions 1 and 2 are much easier to influence given the available data for this analysis.

### Analysis of Outcomes Based on Launch Date
The Excel file containing the required analysis and plots can be found here: https://github.com/ctc43f/Kickstarter_Challenge.xlsx

First I conducted analysis on the success of theater-focused crowdfunding initiatives to determine if there is a target month in which launching the crowdfunding might prove more successful.  This could give Louise the option of delaying or accelerating the project if it would mean a significantly higher probability of hitting target funding, at least based on historical trends.

By using the provided data set and summarizing the success/failure/canceled project counts by month (using a pivotable), we get the following table:

![Image 1: Outcomes Based on Launch Date](/resources/Theater_Outcomes_vs_Launch.png)

It appears that the most successful crowdfunded theater projecs have launched in May and the least amount of successful initiatives have launched in December.  Antecdotally, one might look at the overall plot and argue that the winter months are when it is colder and most of the plays launched in the prior year are showing; as spring comes, playwrites are launching their projects ahead of a summer working session and in advance of the following fall theater season.  One might argue that May could be higher just because that happens to be the month most try to launch their crowdfunding; however, the failed trendline doesn't move up with the same degree of sharpness April-to-May to support that hypothesis.

**The recommendation to Louise would be, based on this analysis, to target a launch of her initiative in May.**

### Analysis of Outcomes Based on Goals
Using the same set of data in the Excel as linked in the prior section, I then proceeded to create a table using the COUNTIFS() function to bucket the results of crowdfunding initiatives, plays specifically, and look for any trends or insights based on the value goal. One notes about my approach: instead of hard-coding the dollar ranges and the text values for outcome into the COUNTIFS() formulas, I instead built adjustable ranges along the perimeter of the Excel table so that the user could adjust the table and easily adjust the analysis.  For example, if Louise asked to further break down the 1,000 to 4,999 range into smaller buckets, instead of having to re-key the formulas I could simply adjust the yellow cells in columns J and K to easily create new ranges and have the formulas update.

See below table with the success and failure trendlines based on increasing target dollar ranges:

![Image 2: Outcomes vs. Goals](/resources/Outcomes_vs_Goals.png)

There are several issues with this visualization that make it hard to quickly gain insight from it:
- Percentage cancelled is 0 in all cases, so having that on the plot adds "noise"
- The success and failure lines are same in magnitude and opposite in direction; the information is redundant and confuses the overall message
- Color choice could be better: I would recolor the lines to green and red to more easily indicate which line is the positive outcome and which is the negative

Using the plot as-is, Louise has an approximate 52% chance of having a successful initiative if she maintains the $10,000 target.  If she were to aim for a higher target, her chances of being successful continue to decrease until the target funding level hits $35K.  Depending on the scope of her play, asking for that much money without the content of a similarly targeted initiative might make it comparatively less appealing and thus not get funded.  Louise could consider crowdfunding at a lower dollar target and seeking the additional funding from investors; initiatives at a target level of $4,999 have around 20 percentage points higher chance of being successful.

**The recommendation to Louise would be, based on this analysis, to launch with a goal of $4,999 and either seeking additional, more traditional funding, or scale back the play to align the budget with this target.**

In the next section I have a couple alternate versions of the above plots that might provide more insight; I will provide updated recommendations for Louise based on those revised visualizations.

### Challenges and Difficulties Encountered
Although I didn't encounter any challenges, I know that there are some areas that might provide challenging when first trying to use Excel:
- The COUNTIFS() function can be hard to read when you have several conditions and are trying to troubleshoot an error
- The Pivotable interface is not the most intuitive when first trying to learn it; the "classic" interface for Pivotables allowed the user to directly drag and drop elements onto the table itself.  This view is still available but buried in a formatting option.
- When you first build a chart and want to modify the data range, it can be hard to adjust where the table is pulling the data and you might end up having additional rows or blanks that are hard to remove.  Often times it might be easier to just rebuild the table from scratch rather than try to repair a "broken" plot.

## Results

### - What are two conclusions you can draw about the Outcomes based on Launch Date?
1. Louise has the best chance of success, based on historical performance, if she launches the crowdfunding initiative in May.
2. The likelihood of being successful decreases as the year progresses from May; it might be better to delay the launch by an entire year if she has issues and is delayed into late summer.

### - What can you conclude about the Outcomes based on Goals?
1. At her current funding target, Louise has about a 52% chance of a successful initiative.
2. If she were to need more money and raise her goal, the likelihood of success goes down until around the $35K.
3. The jump in success at the $35K - $45K levels are visual anomalies in the general downward trendline that runs as goal level increases; there might be something else about those target levels, outside of the goal itself, that determine success.

### - What are some limitations of this dataset?
1. There isn't any detail about the channel or website for the crowdfunding.  A well-known site like Kickstarter has a larger audience than other methods of crowdfunding and it isn't clear the level of exposure of each of these.  
2. There is no geographical information about the crowdfunders that backed the project.  It is hard to determine if the funding came from locals that would want to see the show versus a larger audience donating because of notoriety of the person planning the initiative.
3. Similarly, it isn't clear where the final product, should it be sourced, be made available.  Projects with a larger global reach would be able to get more backers.

### - What are some other possible tables and/or graphs that we could create?
I would look at these additional tables to potentially revise my recommendations:
1. Look at similar plots as what we looked at before but apply additional filters:
   - Apply a geographical filter to align with where Louise is launching the play
   - Limit the results to the last two or three years of data rather than the full 9-year span; if taste in art varies over time, more recent results could be more relevant and provide different recommendations
   - Use some sort of text mining to look for initiatives, regardless of medium, with similar keywords or descriptions to Louise's project and see if outcomes are significantly different
2. I also revised the visualizations we did previously.

   ![Image 3: Outcomes Based on Launch Date v2](/resources/Theater_Outcomes_vs_Launch_v2.png)
   
   The issue I had with the first plot was that it was hard to determine the percentage of success by month because it also considered volume of launched initiatives.  With this plot we can see the percentage of successful campaigns with specific monthly percentages.  While May is still the best month to launch, based on this metric, June is also fairly close.  If Louise is concerned her initiative will get lost in the large volume of projects in May, she might delay a month to get more visibility without significantly impacting her chance of success.
   
   ![Image 4: Outcomes vs. Goals](/resources/Outcomes_vs_Goals_v2.png)
   
   I used a similar design to redo the plot for outcome by dollar range.  I wouldn't change my recommendation in this case, but the visualizain helps provide a more concrete, numeric evaluation of success likelihood relative to goal dollar range.
