# <a name="_nqwqaept32u"></a>Explore AI Excel Integrated Project : Access to Drinking Water
This project is the first of two projects of Explore AI’s where we will be investigating access to safe and affordable water
## <a name="_vzom8ptpg09"></a>Objective
### <a name="_t7zqeaviqfdf"></a>Becoming Familiar with the Dataset
### <a name="_a4qq9xx33k7f"></a>Importing the Data
### <a name="_o18fzr9tjfwp"></a>Investigating Population Size
### <a name="_vp81rmtimtks"></a>Investigating Access by Area
### <a name="_a1axz9khlttv"></a>Investigating access by population size
### <a name="_3qvdx9ljsuow"></a>Investingating Access by income group

## <a name="_iu5je9nmgqdg"></a>Dataset
We’ll take a look at the WHO/UNICEF JMP (Joint Monitoring Programme for Water Supply, Sanitation, and Hygiene) Estimates on the use of water dataset for 2020.We have a total of 16 features (or columns) in our dataset, 12 of which are service-level percentage shares.

**name**

The country or area name.

**income\_group**

The country’s classification according to income group.

**pop\_n**

The national population size estimate in thousands.

**pop\_u** 

The urban population share estimate in percentage points (%).

**wat\_bas\_n**

The estimated national share of people with at least basic service (%)\*.

**wat\_lim\_n**

The estimated national share of people with limited service (%).

**wat\_unimp\_n**

The estimated national share of people with unimproved service (%).

**wat\_sur\_n**

The estimated national share of people with surface service (%).

**wat\_bas\_r**

The estimated rural share of people with at least basic service (%).

**wat\_lim\_r**

The estimated rural share of people with limited service (%).

**wat\_unimp\_r**

The estimated rural share of people with unimproved service (%).

**wat\_sur\_r**

The estimated rural share of people with surface service (%).

**wat\_bas\_u**

The estimated urban share of people with at least basic service (%).

**wat\_lim\_u**

The estimated urban share of people with limited service (%).

**wat\_unimp\_u**

The estimated urban share of people with unimproved service (%).

**wat\_sur\_u**

The estimated urban share of people with surface service (%).

## <a name="_jwvh7274rg72"></a>Tools 
We’ll be using excel to facilitate data manipulation, perform initial assessment of the dataset’s structure and create visualizations

## <a name="_n87cevjhshz3"></a>Approach
### <a name="_ohup1q1wwwhy"></a>Importing the data
In order to investigate the data, we need to import our data, ensuring that it is properly separated into columns and rows.

When importing data, we can either assume that values are comma-separated (as per the file extension) or have Google Sheets automatically detect the separator type.

We see that even if we set the separator type option as "Detect automatically", the column headers are not separated because semicolons were used as separators, rather than commas as in the rest of the dataset.

We now also need to check for other instances of semicolon separators to ensure that values aren’t misinterpreted later.

We know that we have 16 features, so we can check that each column A to P has a column name, i.e. we have 16 columns.

We find five occurrences in different rows across the sheet.So we isolate and fix the incorrectly imported cells.

Let’s create a new feature called value\_cnt that counts the number of cells in a row that has a value. It should count regardless of whether the value is text or number
## <a name="_mwk0pn3uuxv4"></a>Investigating Population Size
We want to summarise the national population size to better understand how the dataset represents the entire world population.

In 2020, the world population was estimated to be 7.821 billion, 55% of which lived in urban areas\*.

Let’s create a summary to compare the dataset population to the estimated world population by creating a new sheet called Global 2020 report.

In this new sheet, we determine the total national population size using the feature pop\_n.we then add the estimated world population (7.821 billion) to this sheet as well.

We also want to compare the world urban population to the dataset urban population. We need the total number of people living in urban areas from our dataset, which we can either compare as a number or percentage to the world urban population value. Let’s create a new feature in our dataset sheet called pop\_u\_val, which is the number of people living in urban areas per country (row). We will use our features pop\_n and pop\_u to determine this new feature.

We know that the estimated world urban population in 2020 was 55% of the total population. Let’s estimate how many people that would be from the world population of 7.821 billion in our Global 2020 report sheet.

We know that the estimated urban share worldwide is 55%. Let’s calculate the urban share in the Global 2020 report sheet using the total national population (pop\_n) and the total urban population (pop\_u\_val)

Let’s calculate the percentage difference to determine the difference between the number of people included in our dataset and the estimated number of people in the world in 2020. 

Let’s also calculate the percentage difference of our urban population totals and percentages.Percentage difference refers to the difference between the relative magnitude of two values, expressed as a percentage of the average of those values.

Let’s create a visualisation to compare the share of the national population living in urban versus rural areas. 

Let’s create a line chart on our Global 2020 report. Our independent variable (the cause) on the x-axis will be the national population size (pop\_n). Our dependent variables (the effect(s)) on the y-axis are the urban and rural population share percentages.

We already have the urban share in percentage in the pop\_u column. We don’t have the rural share but we know we can assume that we only have two groups, urban and rural. In other words, the sum of the urban and rural shares should be equal to 100% for each country. Create a new feature called pop\_r that is the rural share of the population in percentage using the features pop\_u and pop\_n.

Add pop\_n as the x-axis and pop\_u and the newly created pop\_r features as the Series columns. Add appropriate chart and axis titles.

We find that our data visualisation is not very comprehensible, due to some of our pop\_n values being much larger than our other values, in other words, outliers.


![Chart](Aspose.Words.a64968e8-8167-4cd9-aed1-c22bf76c5e12.001.png)

To deal with the outliers in our dataset and thereby increase the readability of our data visualisation we change the unit of our x-axis.

Advantage: Our visualisation is much more comprehensible and we don’t lose information in our dataset for any future

analysis we might need to do.

Disadvantage: Our x-axis doesn’t represent the true difference between population sizes.

Currently, our x-axis (pop\_n) is represented in thousands, i.e. if the pop\_n = 53771.30078 (Kenya’s population size), then the actual population size is pop\_n multiplied by 1000, which equates to approximately 53,771,300 people, or 53.77 million people. Let’s create a new feature in our original dataset sheet called pop\_n (m) which is the national population size rounded up to the nearest million.

We then change the x-axis column in the previously created line chart to the newly created pop\_n (m) column, selecting the Aggregate option in the chart editor under the x-axis options, and Average as the way to aggregate for both series we added previously. Remember to update the x-axis title to appropriately represent the new feature we are using.

We decided to use smooth lines for our line chart and to add a point representation of our aggregated data point.

![Chart](Aspose.Words.a64968e8-8167-4cd9-aed1-c22bf76c5e12.002.png)



## <a name="_1wo4rsfbnxfl"></a>Investigating access by area
We want to investigate what access to water at the different service levels looks like for people in specific types of areas (national, urban, and rural).

We’ll use the measures of central tendency and spread. We calculate the measures of central tendency and spread of the four national service levels.

In our previously created Global 2020 report sheet, let’s determine the maximum of each of the four national water access columns, i.e. \_wat\_bas\_n\_, \_wat\_lim\_n\_, \_wat\_unimp\_n\_, and \_wat\_sur\_n.

We see that our maximum for \_wat\_bas\_n\_ exceeds 100%, which is not possible since 100% access means that every person in that country has access to the service. Let’s go back to our dataset sheet and create a new feature called \_wat\_bas\_n (rounded)\_. We only round up to the decimal to which our value exceeds 100% because we are not rounding any of our other three service columns. We can use a filter on our new column to check that we now only have values below 100%.

On the Global 2020 report sheet where we calculated the maximum of each of the water levels, we change the reference to wat\_bas\_n on the function to the newly created feature, \_wat\_bas\_n (rounded)\_.


` `We see that we get a #VALUE! error for our maximum function. Looking at the typical values in our \_wat\_bas\_n (rounded)\_ column using a filter, we see that we have #VALUE! errors on our rounding function. Let’s use the filter and change the #VALUE! entries in this column to a text NAN value. Now our maximum function should work in the Global 2020 report sheet.

Since we’ve already determined the maximum values, we know that we don’t have any values above approximately 37% for \_wat\_lim\_n\_, \_wat\_unimp\_n\_, and \_wat\_sur\_n\_. Let’s also determine the minimum values for all four national service levels in the Global 2020 report sheet.

For a normal distribution, we expect that the mean, median, and mode would be equal. Let’s calculate these three features for each of the four service level columns namely, wat\_bas\_n, wat\_lim\_n, wat\_unimp\_n, and wat\_sur\_n.

We see that the mean, median, and mode are not equal for any of the four features. Let’s also calculate the interquartile range (IQR) and standard deviation for these four features to gain some insight into how the data are distributed.

For wat\_bas\_n, we see that the mean is relatively high and the interquartile range is about a tenth of the range, which indicates that our data are concentrated around a point closer to 100% than 0%. This means that the majority of people represented in the data have access to at least basic water services on a national level.

We then Visualise the five-number summary of the four access features across the three different types of areas .Let’s create a box and whisker diagram (called a candlestick chart in Google Sheets) in the Global 2020 report sheet from our measures of central tendency and spread summary for all 12 features namely, wat\_bas\_n, wat\_lim\_n, wat\_unimp\_n, wat\_sur\_n, wat\_bas\_r, wat\_lim\_r, wat\_unimp\_r, wat\_sur\_r,wat\_bas\_u, wat\_lim\_u, wat\_unimp\_u, and wat\_sur\_u.

![Chart](Aspose.Words.a64968e8-8167-4cd9-aed1-c22bf76c5e12.003.png)



## <a name="_qwq1nkqb8w05"></a>Investigating access by population size

We want to investigate what access to water at the different service levels looks like for different population sizes. We start by visulaising the national access to water on all four levels based on the national population size.

In our previously created Global 2020 report sheet, let’s create a bar chart. Since we want to investigate how population size affects access levels, population size (pop\_n) will be our independent variable (the cause), and our four access features (wat\_bas\_n\_, wat\_lim\_n\_, wat\_unimp\_n\_, and wat\_sur\_n\_) will be the dependent variables (the effects).

Because our access levels are percentages and we know that an individual or household can only be at one of those levels, we’ll change our bar chart to a 100% stacked column chart.

As in our investigation on population size previously, we observe that using the original population sizes in thousands is relatively unintuitive because the bars are too narrow and we have too many of them.

![Chart](Aspose.Words.a64968e8-8167-4cd9-aed1-c22bf76c5e12.004.png)

Folliwing that, we visualise the urban access to water on all four levels based on the urban population

In our previously created Global 2020 report sheet, let’s create another 100% stacked column chart, similar to what we created in A, but only for urban areas. Let’s use urban population share (pop\_u in percentage) as our independent variable.

In order to avoid a messy bar chart, we are going to create a new feature called pop\_u (rounded), which is the urban population share (pop\_u) rounded to the nearest whole number. Use this new feature as the x-axis in the 100% stacked column chart, and set the aggregations to Average.

We notice that our x-axis isn’t arranged from zero to a hundred, as expected. Let’s order our dataset based on pop\_u (rounded), before we consider any insights.
## <a name="_ckd6455kx887"></a>Investigating access by income group
We summarise the dataset to group and investigate by the four income groups 

In our previously created Global 2020 report sheet, let’s create a pivot table. Because we want to group by income group, we will set our rows to the income group feature, income\_group.

Our values are the sum of the population size (pop\_n), the average urban share (pop\_u), and the average national share of basic (wat\_bas\_n), limited (wat\_lim\_n), unimproved (wat\_unimp\_n), and surface (wat\_sur\_n) access.

Let’s also visualise our summary data. In order to better investigate the link between income group and the other features, it would be useful if we could sort our x-axis on income groups more appropriately. Let’s convert our text column income\_group in the dataset sheet to numbers, where NAN is 0, Low income is 1, Lower middle income is 2, Upper middle income is 3, and High income is 4.


