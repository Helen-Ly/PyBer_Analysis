# PyBer Analysis

## Project Overview

The CEO of a python-based ride sharing app company, PyBer, has asked you to perform exploratory analysis on data in some large csv files. To tell a compelling story in the upcoming presentation, you are to create several types of visualizations.

  1. Create a scatter plot showcasing the correlation of average fare to the total number of rides (per city).
  2. Create a box-and-whisker plot for the following:
      - Number of Rides and City Types
      - Fare ($USD) and City Types
      - Number of Drivers and City Types
  3.  Create a pie chart for the following:
      - Percentage of Total Fares by City Type
      - Percentage of Total Rides by City Type
      - Percentage of Total Drivers by City Type

## Resources

  1. Data Source: city_data.csv, ride_data.csv
  2. Software: Python 3.7.6, Jupyter Lab 1.2.6
  3. Library: Matplotlib.pyplot, Pandas, NumPy

## Summary

Throughout the process of creating the visualizations, we have decided to use the company's color theme (gold, sky blue, and coral) to present our analysis.

### 1. Scatter Plot

The scatter plot showcases the correlation between the Average Fare ($) to the Number of Rides (per city). As we see in the legend, there are 3 city types (Urban, Suburban, and Rural). Each city type has its own color and the size of its marker is the Average Number of Drivers in each city.

![](https://github.com/Helen-Ly/PyBer_Analysis/blob/master/Analysis/Fig1.png)

 As we look at the plot, we are able to tell that Urban city types has a higher Average Number of Drivers in each city as opposed to Rural city types, with the fewest Average Number of Drivers.

### 2. Box-and-Whisker Plots

Next we decided to create box-and-whisker plots as it allows us to see if there are any outliers. Aside from the outliers, this plotting method provides a lot of information for each city type.

1. Number of Rides and City Types

The first plot shows the correlation between the Number of Rides and City Types.

![](https://github.com/Helen-Ly/PyBer_Analysis/blob/master/Analysis/Fig2.png)

Looking at the plot, the first thing we notice is that the outlier for the Urban Ride Count is 39. From this, we are able to find which city has the highest rider count. Another thing to notice is that Urban cities has 3 to 4 times higher Average of Rides than Suburban and Rural cities, respectively.

2. Fare ($USD) and City Types

The next plot showcases the correlation between Fare ($USD) and City Types.

![](https://github.com/Helen-Ly/PyBer_Analysis/blob/master/Analysis/Fig3.png)

Unlike the first plot, we don't see any outliers in this plot. We are also able to see that Rural cities has a higher Average Fare as opposed to Urban and Suburban cities.

3. Number of Drivers and City Types

In the third plot, we take a look at the correlation between Number of Drivers and City Types.

![](https://github.com/Helen-Ly/PyBer_Analysis/blob/master/Analysis/Fig4.png)

Once plotted, we see a big difference between the plots before and between the city types. Firstly, there are no outliers. However, the Average Number of Drivers is Urban cities is a lot higher than Suburban and Rural cities.

### 3. Pie Charts

Box-and Whisker plots may have a lot of information, but to analyze the difference between the 3 city types may be hard. Pie charts are a good way to show these differences by percentage.

1. Percentage of Total Rides by City Type

With reference to the first box-and-whisker plot, we created a pie chart that shows the Percentage of Total Rides. 

![](https://github.com/Helen-Ly/PyBer_Analysis/blob/master/Analysis/Fig6.png)

As we see in this chart, this presents a clear picture that Urban cities has a higher Percentage of Total Rides with 68.4%, and Rural cities with the fewest with 5.3%.

2. Percentage of Total Fares by City Type
 
We next took a look at the Total Fares by City Type.

![](https://github.com/Helen-Ly/PyBer_Analysis/blob/master/Analysis/Fig5.png) 
 
 Just like the first chart, Urban cities holds the highest Percentage of Total Fares with 62.7% and again, Rural cities with the fewest with 6.8%. Both pie charts have similar percentage distribution between each city type.

3. Percentage of Total Drivers by City Type

Our third pie chart presents the Percentage of Total Drivers by City Type.

![](https://github.com/Helen-Ly/PyBer_Analysis/blob/master/Analysis/Fig7.png)

Just like the other pie charts, Urban cities dominate the pie chart. However, we see that the Urban cities holds 86.7% of the overall Total Drivers, Suburban cities with 12.5%, and Rural cities with 0.8%. These charts helped us visually get a better picture from the analysis we performed.

## Challenge

The presentation went very well, especially with the aid of your visualizations (which you can find in the *Analysis* folder). You have a new assignment to create an overall snapshot of the ride-sharing data.

  1. Create a summary table of key metrics of the ride-sharing data by city type.
  2. Create a multiple-line graph that shows the average fare for each week by each city type.
  
## Method

### 1. Part One: Summary Table

To create this table, we collected the following data for each city type with the *groupby()* function:

   - Total Rides
   - Total Drivers
   - Total Fares
   - Average Fare per Ride
   - Average Fare per Driver
   
After collecting the above information, we created a Summary DataFrame with the appropriate columns and applied formatting where appropriate.

| |Total Rides|Total Drivers|Total Fares|Average Fare per Ride|Average Fare per Driver|
|-|-----------|-------------|-----------|---------------------|-----------------------|
|Rural|125|78|$4,327.93|$34.62|$55.49|
|Suburban|625|490|$19,356.33|$30.9|$39.50|
|Urban|1,625|2,405|$39,854.38|$24.53|$16.57|

When we briefly look at the Summary DataFrame, we see that Urban cities have higher Total Rides, Total Drivers and Total Fares as opposed to Rural and Suburban cities. However, Rural cities have a higher Average Fare per Ride and Average Fare per Driver than Urban and Suburban cities.

### 2. Part Two: Multiple-Line Plot

For the multiple-line plot, we plotted the sum of the fares for each city type with the following method:

   - Renamed the columns and set the Date column as the index
   - Created a new DataFrame with only the columns we wanted with the *copy()* function
   - Set the index to the datetime data type
   - Calculate the *sum()* of fares by city type and date using *groupby()*
   - Reset the index and created a pivot table DataFrame with the Date as the index and City Type as the columns
   - Create a new DataFrame from the pivot table on the given dates '2019-01-01':'2019-04-28' using *loc*
   - Create another new DataFrame by setting the previous DataFrame you just created with *resample()* in weekly bins and calculate the *sum()* of the fares for each week
   - Plot the DataFrame using *df.plot()* using the graph style *fivethirtyeight*

After collecting the data and plotting it, we ensure that all the labels, title, and the size of the chart was correct and big enough to see the data.

![](https://github.com/Helen-Ly/PyBer_Analysis/blob/master/Analysis/Fig8.png)

In this multiple-line plot, we see that data fluctuate through January to April and throughout this fluctuation, the plot shows that Urban cities have a higher Sum of Fares than Suburban and Rural cities.

## Challenge Summary

When we look at the data separately, it is hard to see the correlation. However, when you combine them, they tell a compelling story. Together, we were able to pull the following implications:

  1. The reason Urban cities have the highest Total Rides and Total Fare is because they have the highest Total Drivers.
  2. The reason Rural cities have the lowest Total Rides and Total Fare is because they have the lowest Total Drivers.
  3. You may be wondering about the Average Fare per Ride and Average Fare per Driver. With so many available drivers in Urban cities, and the various destinations within those cities, some of the Fare will be lower than others. It is evident when you average out the fares per driver and per ride. 
  4. On the opposite end of the spectrum with Rural cities. The destinations may not be down the road, and with only a few drivers available, there will be a higher rate for the drivers and the fare for the trip will be higher. This is also evident when you average out the fares per ride and per driver and the reason why Rural cities have the highest Average Fare per Ride and per Driver.
  5. The proximity of the rides and the number of drivers available affects the Average Fare per Ride and per Driver.
  6. The multiple-line plot only shows 4 months and though there aren't many fluctuations, there are small spikes in March and April. This could be a result of people going out because the weather is starting to warm up.
  

## Usage

If you would like to run this code on your own computer and play around the numbers to get your own results:

   1. Download Anaconda to your computer and install Jupyter Notebook/Jupyter Lab if you don't already have it.
   2. Create a Development Environment that has all the required packages need to run this code.

        - I am using Windows, so the following is how to open it on Windows.

        - Open your Anaconda Command Prompt and type the following:

           > conda create -n PythonData python=3.7 anaconda

   3. Download the files you would like to run and save them in a folder together.
   4. Open the Anaconda Command Prompt (if not already opened) and navigate to the folder holding your downloaded files.
   5. Once you are in that directory, type jupyter lab or jupyter notebook.
   6. It will open a webpage and you will have access to the two files in your side panel.
   7. If you would like to create your own files, ensure you have imported all the required dependencies.
