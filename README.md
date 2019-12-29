The list is scrollable: Click and drag / mousewheel / arrow up or down to see all the categories!

The yellow line indicates where you are on that day/time chart. The line only updates when you load a new category.

This visualization is of Yelp check-ins to certain categories of businesses over time. A business can have more than one category. The data is from an area in Arizona, collected between January 19th to March 12th, 2013.

The data was originally in JSON and provided by Yelp for a [contest held at kaggle.com](https://www.kaggle.com/c/yelp-recruiting). To make it easier to aggregate, I split it up into tables and imported it into a MySQL database. I made the tables manually and imported much of the data by exporting the JSON to a CSV to match the table structure and imported the data from CSV to the database. The exception to this is business categories, since that was the only data that was relational and not split up by the original JSON files. First I used ruby to make a distinct list of the categories of businesses, imported them, then used another ruby script to build INSERT statements to associate businesses in the database to those categories. I then wrote a query that aggregated it by business category and hour of each day. A backup of the database and the work to generate it is available at [https://github.com/gelicia/yelpRecruit](https://github.com/gelicia/yelpRecruit)

With the data all nice and relational, I queried the checkin data grouped by business category and exported the result as a CSV to use in this visualization.