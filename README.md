# Excel Kickstarter Analysis

## Overview of Project
The goal of this analysis was to provide a data driven rational to assist Louise in deciding when to launch her Kickstarter.
This analysis consisted of two separate and distinct tables to help provide insight in to two primary concerns when running
a Kickstarter campaign. What time of year are they most successful and what is a goal that is likely to succeed. Timing and
scaling a campaign correctly can have profound outcomes, **using multiple models I believe I have found both an ideal month
and ideal cash goal**.


## Analysis and Challenges
First impressions of the data was that the set was neat and clearly organized. The with several thousand individual campaigns
the results of the different queries were statistically significant and worthy of critical usage. This analysis was not a
simple task to complete. Many mistakes were made, and the results initially did not provide much, if any usable outcomes.
To first allow for greater depth of understanding the data needed to be further refined as to provide the ability to track
trends over the course nearly a decade. To achieve this the year of campaign launch was separated from the month, this was
done by adding another column titled years and populated using the  **`Years()`** function within Excel. This code versus a 
change to the formatting created a dataset that was more consistently searchable. The initial results did not provide much
in the way of useable analysis, with chart that had flipped axis, more tuning needed to be done. Outcomes and Date Created
Conversion got put into the right spots in Columns and Rows respectively. With the Parent Category and Years being used as
the filters I was able to successfully create a meaningful table with a correspondingly useful graph. Seen below:

![This is an image that shows the outcomes of Kickstarter campaigns based on the month that they are launched] (https://github.com/dh4rt/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png)

This graph indicates a number of trends that should be considered when launching a campaign.  The absolute worst month to
start a campaign are the months of November and December. The reasons for this are not totally clear but I believe it is a 
multitude of factors. The most obvious of these is that in Western world these two months are very expensive for many folks,
with two to three holidays that often stress travel and costly material expenditures American Thanksgiving, Christmas, and
Hanukkah that could cause a decision to be made on in terms of where money is spent. Far and away the most successful month
for theater related campaigns to launch is the month of May with the rate of successful campaigns more than doubling that of
failed campaigns. June follows up in close second as month with most successful campaigns launched, and repeating the pattern
of more than doubling the rate of success to failure. These two months have the greatest rate of success to failure out for
the entire calendar year. Now as to why that is remains unclear to me. It does not correlate with Federal Government fiscal
years, it does not correlate with major holidays associated with gift giving, and it does not correlate with when the Tony
awards normally happen (Mid-June). The only things I can think of that might have some effect is tax returns from the US
Governments and graduations.

The next analysis performed needed to determine what if any information could be gleaned from the monetary goals of theater 
based campaigns.  The first decision to be made was how to separate the goals into groups, ultimately the decision was made
to group together in $5,000 incriminates starting at $1,000 and ending at $50,000+ this gave. What was then done was to us the
**`=COUNTIF`** feature with multiple conditionals for example the first input 
**`=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"successful",Kickstarter!$O:$O,"plays")`** was used, what initially was 
a source of great frustration was the filters applied to the Kickstarter page had no effect on the count displayed in the
Outcomes Based on Goals which is why the conditional of 'Kickstarter!$O:$O,"plays"` was used to give us the specific data
needed for this analysis to be successful. This table was the most difficult part of the analysis for a number of reasons.
The most troublesome part of the table was making sure code was accurate to both the tiers of funding and the results needed.
Eventually what I did when I was able to get the Number Successful column working correctly was to drag the code across the
table and adjust for Failed and Canceled while still having the coding for the different tiers still be and operational. This
image can be seen below:

![This image shows a graph depicting the percentage chance of success, failure, and cancelation of a Kickstarter campaign based on the financial goals] (https://github.com/dh4rt/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png)

This graph indicates a very shaky at best correlation between the financial goals and the likelihood of the campaign’s success.
The first-tier goal `<$1000` has the highest rate of success at 76% with $1000-$5000 having the second highest success rate at
73% and those are both good rates of success that should be considered. The problem is that from there the rates of success
largely plummet dropping to low of 20% rate of success at the $25000-$29999 range only to shoot up and plateau to a success
rate of 67% for $35000-$39999 and $40000-$44999. From there your likelihood of success is nil, the next two tiers, the two
highest for the record having a combined rate of success at 13%. So, what this data tells us is that plays have two sweet spots
for success `<$5000' and between `$35000-$45000' beyond that plays are a really risky venture for folks to use as their cause.
I genuinely don’t know what the cause for this is and because the data is so up and down, the rate of success looks more like a
roller coaster than an ideal Kickstarter strategy. Some of the returns are genuinely baffling, the rate of success for campaigns
between $20000-$34999 is less than 50% but for some reason between $35000-$44999 the likelihood of success then jumps by more 
than double. What may contribute to this is the general public not totally understanding just how expensive it is to put on a
professional level production. 
	

### Challenges and Difficulties Encountered
The challenges faced in this analysis centered largely around the small details in filtering and separating the data amongst the
Pivot and normal tables. To get the Years and Parent Category filters working in the correct order had much trial and error.
This dataset at times felt difficult to fully grasp with the scope of what is and is not a successful campaign goal and type
seeming to have very little correlation for success, at least within the scope of what Lousie wants to achieve. Another of
the difficulties faced was getting the data to filter correctly on to tables, this is largely due to my own misunderstandings
of how the tables would work, needing to specify for instance that the plays subcategory needed to be specified on the table
and not just filtered through the primary Kickstarter sheet was not an intuitive piece of code to write.  A challenge that I
had not considered until a discussion with a classmate was the accessibility of the graphs used, the initial color scheme that
excel provided was not use for those with certain types of colorblindness. So making sure that Lousie had useable graphics that
could be shared with a variety of people provided a challenge that was entirely unexpected.

## Results
In conclusion there are a number of take aways to discuss and consider before moving forward with a Kickstarter campaign.  I
feel that there are two primary conclusions that can be drawn from the **Outcomes based on Launch Date** and those are
- **Timing is crucial**
When you want to launch your campaign can make your success more likely, with that in mind **May is the best month
to launch a Theater specific campaign, with the successful campaigns more than doubling those that failed.** Conversely
October-January has the closest margin for failure, with December in particular being more likely to fail or be
cancelled than to succeed.
- **The likelihood of having of Failure is never more than the Success rate**
At no point during the course of the year is your campaign likely to be cancelled, in fact the rate of cancelation
never rises over 10%. This tells us that Theater Kickstarters regardless of launch date with will either be
successful or they wont, and while that binary is stark it provides some comfort in that even youre never more likely
to outright fail than succeed at any point in the year.



- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
