# September 30, 2024

*This is based off a Kaggle lesson for the groupby operation.*

Often we want to group our data, and then do something specific to the group the data is in. We do this with the groupby operation.

In these exercises we'll apply groupwise analysis to a dataset of 130,000 wine reviews from Wine Magazine.

1. Who are the most common wine reviewers in the dataset? Create a `DataFrame` whose index is the taster_twitter_handle category from the dataset, and whose values count how many reviews each person wrote.

2. What is the best wine I can buy for a given amount of money? Create a `Series` whose index is wine prices and whose values is the maximum number of points a wine costing that much was given in a review. 

3. What are the minimum and maximum prices for each variety of wine? Create a DataFrame whose index is the variety category from the dataset and whose values are the min and max values thereof.

4. Create a `Series` whose index is reviewers and whose values is the average review score given out by that reviewer. Hint: you will need the taster_name and points columns.

5. What combination of countries and varieties are most common? Create a `Series` whose index is a MultiIndexof {country, variety} pairs. Sort the values in the Series in descending order based on wine count. For example, a pinot noir produced in the US should map to {"US", "Pinot Noir"}. This is new, but the hint is to pass a list of two column names into the groupby function. Then, you'll need to look up how to sort.
