# Project 6 - Data Visualization with d3.js

## Best and Worst London Boroughs by Crime Type

### Summary

* Visualization link : http://bl.ocks.org/kaltera/raw/af222b601279ae354557/
* Original Visualization : http://d3viz.tk/
* Note that indexV1.html is not commented, I only commented the final html file

This project is about creating a similar map as London Metropolitan Police on the best and worst London Boroughs in terms of criminal activities available here : http://maps.met.police.uk/ . I wanted to give the reader the ability to drill down into specific categories and to automatically show some statistics

The visualization includes a map of all 32 London boroughs except London City. Depending on the crime category selected through the radio buttons on the right, a colour is assigned to each borough related to the number of crimes committed.

### Design

As my first visualization project did not work out due to the lack of story in the dataset, I decided to embark in a new project involving some other d3 skills : maps. I therefore looked after a geojson file which would indicate the boroughs boundaries in order to draw them.

Once those borough boundaries were drawn, it felt slightly odd as there was only lines on the screen and I wanted to let the user know that it was corresponding to London Boroughs. I therefore decided to add a topographic map in the background to give out more context. Unfortunately I figured out it was easier to use Mapbox in order to have both topographic and boundaries information on the same map but I though it might be off-topic as mapbox is a additional library to use. To this end, I had to play around with the map in order to position it perfectly over the boroughs.

On the right side of the map I have added radio buttons where the user can choose which crime category he wants to focus on. A transition is available on the colours and you can see each borough changing colours smoothly from one crime type to the other.

In order to give more context to the reader, I decided to add a tooltip as soon as the reader puts his mouse over the boroughs. Once this happens, the borough's name appears and a table is being updated on the bottom-right of the page where you can see more detailed information for the crime type. It drills down into sub-categories for each crime type and indicates the number of occurences.

As the initial goal is to indicate which boroughs are worst or best in London, I have also added a ranking for each borough out of the 32 in total. This ranking is available on the summary table as soon as the reader puts his mouse over a specific borough. This ranking changes depending on the crime type chosen as the data adapts automatically.


### Feedback

Most of the feedback has been received from the Udacity forum on this link : https://discussions.udacity.com/t/p6-feedback-best-and-worst-london-city-boroughs/30331/8

###### Feedback No.1 : Teja

* Version 1
  * The visualization looks great! It would be helpful if the number of crimes was specified when I click on different options
  * For example, something I noticed when I selected the "Fraud and Forgery" option. The opacity of all the boroughs are set to high values. How many crimes does a specific opacity indicate? When compared to what I see for the other option (Drugs, Burglary,...) it leads me to believe that Fraud and Forgery is the crime type that occurs the most. It might be possible that there were only 100 crimes corresponding to Fraud and 5000 corresponding to robbery but occurrences of Fraud may have been spread out more uniformly across the map so all the boroughs have high opacity.
  * The scaling of opacity is something I would think about changing, or maybe just display an explicit scale depicting the mapping of opacity to number of crimes.
  * Apologies, I didn't notice the crime count right away. Had to scroll to the right. So the opacity is actually for crime per capita? I think that should be something explicitly mentioned


###### Feedback No.2 : Andrew

* Version 1
  * Put the years into the title (perhaps on a second line) -- they crowd the picker and don't really have much to do with picking the crime type
  * When i use at slightly larger browser text sizes (ctrl+) the text with population wraps badly. I think it would be better to have population on next line
  * The heading font above the crime type radio buttons, and the crime counts are very large -- i suggest reduce them
  * Use "Crime Type" not "Crimes Type"
  * I think that each crime type uses the same scale .. Perhaps try using one scale that ranges from the max to the min of the whole dataset. As an example, if you look at "other " the color differences seem meaningful, but in fact the numbers are so small that the differences are most likely meaningless. Perhaps you should leave out this other category entirely and that may then give a better scale range as well
  * The crime types are alphabetical - perhaps order them from highest to lowest, and maybe coloring the background of the text in a scaled color may also convey which crimes are most common.
  * I think it is quite common to express population related numbers as "per 10,000" people. I may be wrong though. Look at some united nations charts.

### Changes

I tried to reflect most of the changes on the visualization, mostly around the font-size and order of crime types, however the scale remained an issue as I could not use the same scale (per capita) for all the different categories. For instance the Theft has an average of 25,000 occurence while the Sexual Offence has around 3,000. As suggested by Andrew I took a look at some of the charts and decided to follow the example of London Met as it's a scale going from High to Low and it is convenient in this case when similar scales cannot be used across the different crime categories.

I however made all the changes and suggestion related to the aesthetics and also removing some categories as the scale was way too low (ie Fraud & Forgery)

### Resources

* d3.js Documentation https://github.com/mbostock/d3/wiki
* Maps Udacity d3.js Course
* Color Brewer http://colorbrewer2.org/
* Tooltip on mouseover http://stackoverflow.com/questions/10805184/d3-show-data-on-mouseover-of-circle
* Legend Udacity d3.js course
* Geojson map http://geojson.io/#map=10/51.4917/-0.0883
* Table Style http://cssmenumaker.com/blog/stylish-css-tables-tutorial
* Background Image as patterns http://stackoverflow.com/questions/19033034/can-i-use-images-as-the-background-rectangles-for-d3-treemaps
