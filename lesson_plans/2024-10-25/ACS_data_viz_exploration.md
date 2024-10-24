1. Go to Canvas and download from Files -> Data Sets the file acs_cleaned.pickle (this is the cleaned up version of the acs data we looked at last class)
2. Upload the file to Google Colab.
3. Run
   `import pandas as pd`
   `acs=pd.read_pickle('acs_cleaned.pickle')`
4. I want to you explore relations using data visualization. You should aim for at least 6 good quality visualizations that span number of variables and variable types (one numerical, one categorical, two numerical, one numerical one categorical, two categorical).

Please keep in mind that the cases we are working with in this dataset are people. 
Any relationships you see in the data should not be taken as causal (correlation does not imply causation!). 
Moreover, historical and ongoing injustice can lead to differences between groups when looking at this kind of data.

Some suggestions to get you started (don't just do these):
* Income distribution for men and women in the dataset who earn less than $100,000. I recommend looking at this data with both a
  side-by-side box and whisker plot and with two seperate histograms.
    * For the box and whisker plots, can you plot a subset of the data that makes the number of outliers smaller? 
    * For the histograms, perhaps try to put both distributions on the same axes with transparency?
* Visualize the counts of the variable age using a histogram. Are there any oddities in the data? What do you expect explains any oddities?
* Visualize the counts of education level in the data set. Do you think this matches the distribution of "highest education achieved" in the country? If not, can you better approximate this distribution?
* Make a side-by-side barplot of education level by marital status.

