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

In the next 

### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
