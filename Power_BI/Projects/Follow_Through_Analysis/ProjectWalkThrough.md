## Problem Statement

This report helps schools prepare for the start of school. The number of expected students in August is a metric used to plan for teacher/staff allocations let alone a number of other resources. Unexpected student “No Shows” can highly impact this planning. What’s more, each student that does not follow through and attend the school they were offered a seat to translates to wasted resources by registrars and school staff in preparation for that student. Identifying which students are not following through, especially to which schools and grades, can inform planning and suggest areas for increased efforts or even policy change to ensure resources spent preparing for each student are not wasted.    

### Steps Followed

 - Step 1 : Use Python to create a dummy data set. Code can be found here. After the dataset was created, for the purpose of showcasing how the data could show patterns/trends with Power BI, I manually adjusted the data to follow certain pre-determined patterns. (Noted. This is not at all how one should normally analyze real data.)
 - Step 2: I like to show when the data was loaded on my reports. To do so, I click “Enter Data” under Transform Data, setting the table title to “Last Date Refresh” and enter this Power Query (M) code to return the current date/time.  
 - Step 3: To look at Apply Grade by Elementary, Middle and High School, I right click the column for Apply Grade, select New Group to create a new column, grouping grades 1-5 for Elementary, 6-8 for Middle, and 9-12 for High School. 
 - Step 4: I make the measures for the reports cards and visuals, measures can be found here. 
 - Step 5: Under View, I pick the theme “Accessible Title” for the report. 
 - Step 6: I add in my visuals for each of the variables I want to analyze: Apply Grade, Year, School Choice Rank, and Response to Offer. 
 - Step 7: I want to toggle between visuals showing percentages and the same visuals showing the data totals. To do so, under View, I click Bookmark and Selections to show these two extra panes. Then I add two new Blank buttons and rename them to Totals and Percentages. Next I add two Bookmarks and label them FollowThroughTotals and Follow ThroughPercentages. Then, I use the Selections pane, for when the user selects the “Totals” button, I select each visual that should be visible and each visual that should be hidden (clicking the eye icon next to it to hide it), and with those selected, I “Update” the Bookmark FollowThroughTotals. 
 - Step 8: Users new to Power BI often don’t know how to filter using the visuals or export data, so I like to include small notes explaining these things. Following along the steps above, I created two new buttons and bookmarks to accomplish this, using the Selections and Bookmarks page to set each button/bookmark’s visuals. 
 - Step 9: Finally, I wrote a small summary of the key findings and published to Power BI!

Click the Power BI link below to interact with the report.

https://app.powerbi.com/reportEmbed?reportId=4657b604-ccd2-4350-966a-7c5dbda945a3&autoAuth=true&ctid=846a16a1-a7b3-46bf-8274-29f7edceec4d
