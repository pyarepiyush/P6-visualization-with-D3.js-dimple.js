# P6 - Data Visualization
## Prospect Loan data visualization
**Udacity Data Analyst NanoDegree Project6 submission**


#### Summary
This Project creates chart showing % of loan-status values by their Prosper score and income range values. 
It uses dimple.js for creating the main chart, and also uses D3 to set overall attributes.  This chart has interactive legend, which can be used to filter out loan-status values.

Here is the screenshot of the viz:
[Screenshot](Capture.PNG)

#### Design

I used the templates available in dimplejs.org website, and well as the course to get design ideas. 

I decided to go for 100% stacked column-chart, showing the % of measure in each column that adds up to 100%. Here are the reasons for selecting this chart:
* I wanted to show what % of loan-types contributes to the whole. 
* This chart can show relative difference in Loan-Status across different Prospect Scores and Income Ranges. 
* Normal stacked bar-chart displays absolute counts, which does not allow easy comparison across different dimensions, i.e., there might be only 10 loans with Prosper Score of 1, but there might be 1000 loans with Propser Score of 10. So, absolute comparison of Loan-Status might not be fair.
    
I used legend to identify Loan Status values which are represented by colors. Although colors are great way to visually distinguish between discrete values, it is not possible to guess the values each color represented. Therefore, legends help us identify associated with each color.

Tooltips are great way to add interactivity, and add more information that might be helpful to the user. Once the user looks at the whole chart, s/he would want to know more about one particular element of the chart. Tooltips allow us to add more information that we'd otherwise not be able to add.

From the feedback that I collected below, I performed following improvements:
* The values for Prospect-Score, Income-Range and Loan Status were not sorted. So I sorted them in the script. Here is the [git commit](https://github.com/pyarepiyush/P6-visualization-with-D3.js-dimple.js/blob/7eaaf0a5f842ec63a2365fb74af08dfe3c49e9b5/index.html) before properly sorting the values.
* The default colors for loan-type was not intuitive. So, I manually assigned appropriate colors to each value. Color 'Red' was used to represent Bad Loans, 'blue' for current and 'green' for completed. Universally, 'red' represents negative outsome and 'green' represents positive outcome. I debated using either 'blue' or 'orange' for completed loan, and settled on blue because it stood out better than orange. Here is the [git commit](https://github.com/pyarepiyush/P6-visualization-with-D3.js-dimple.js/tree/a49e8681ede16426cce11098ff60fd975ddb1170) before reassigning colors. 
*  I removed the clickable legend because I realized that it wasn't adding any additional value to the visualization. 100% stacked bar chart makes sense only when we look at individual elements as part of the whole. Therefore, i decided to remove this feature. #4 review is from udacity reviewer for this [git commit](https://github.com/pyarepiyush/P6-visualization-with-D3.js-dimple.js/tree/e458e46fc209045cb1987955d5ad95338b1ff282) discussing this issue.


#### Feedback
Following are the feedback I collected from 3 individuals:
 * **Person 1:** 
 	1) Income Range values are not ordered (from lower to higher income), so it is difficult to follow loan-status values based on income.
    2) Bad Loan has green color and Completed loan has red color, which is exactly opposite of what it should be. Most peoplke associate Red with 'Bad', and green with 'Good'.
    
* **Person 2:**
	1) Should add some kind of header, and descriptive sub-header, as well as legend title.
    2) Will be nice if user can play around with different filters.
    
* **Person 3:**
	1) The x-axis is confusing. It has two dimensions (Prosper-Score and Income-Range), however, only values for Prosper Score is labeled in the axis (1-11). Values for Income Range is not labeled, so it is hard to associate a bar with an Income Range. 
    
* **Person 4 (Udacity reviewer):**
	1) Well done with the bars, the reader can easily understand that we are showing some numerical values in the plots. However, the design choices don't fully foster communication between the reader and the visualization.The percentage shown in the bars works well when a reader selects all the three loan types but showing a 100% value in the bars when a reader selects only one or two loan statuses is confusing.

		Required

		When a reader selects only one loan status the bars should not show him 100% but only the percentages attributed to that loan status. The same thing applies when a reader selects two loan status from the legend. The percentage of the bars should be the sum of the individual percentages of the selected loan types.
    

#### Resources

[Bar Labels](http://dimplejs.org/advanced_examples_viewer.html?id=advanced_bar_labels)

[Interactive Legend](http://dimplejs.org/advanced_examples_viewer.html?id=advanced_interactive_legends)

[Udacity Data-Analyst Nanodegree - Data Visualizations](https://classroom.udacity.com/nanodegrees/nd002/parts/00213454010)

[Let's Make a Bar Chart](https://bost.ocks.org/mike/bar/3/)

[dimple documentation](https://github.com/PMSI-AlignAlytics/dimple/wiki)






 