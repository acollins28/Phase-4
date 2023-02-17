# Overview


In the 2010s, Texas has become a hotbed of business development in major cities and surrounding suburbs. As a result, this has attracted more working professionals to the state who buy homes. Investors are seeking to capitalize on this trend, especially since interest rates are low and home buying rates are at all-time highs.

# Business Problem


Tom Jones, a business owner in Texas, is looking to diversify his investment portfolio by investing in residential properties, particularly single family homes. He has asked us to find the best investment opportunities in locations that are near the offices of his business, so that they can be near where he already travels in the instance he wants to see the property himself.

# Data


We pulled home price data from Zillow to do our analysis. Zillow's data included the mean home price for a given zipcode thorughout the United States, measured at the first of every month since 1996. We narrowed our search to only include zipcodes in the Dallas-Fort Worth, Houston, Austin, San Antonio and McAllen metro areas. From there, we determined the 20 zipcodes with the highest return on investment in the last five years, out of a pool of 587 possible zipcodes.

Because of the price bubble and ensuing crash in 2008, we decided to only use price data from January 2010 onward.

As a pre-processing step, data was transformed from wide to long format in a process called melting. Because price avereages were the same thing being measured repeatedly overtime, we had to convert to univariate long format with the date of each measurement set as the index. This allows us to parse through any slice of time we want, and train and build models more easily. Rather than having to iterate over columns of measurements for each zipcode, we only had to iterate of columns of zipcodes for each measurement, making our loops incredibly fast.

# Methods


We used the auto_arima package to create SARIMA models and forecast mean home values two years into the future. 

Mean Absolute Percentage Error (MAPE) was used to determine how good models were. MAPE is a measure of how far off predicted prices were from real prices, as a measure of percentage. Models with a MAPE of less than .5 (off by less than 50%) were considered usable, and the lower the percentage the better. 

Below is an example of a model that was used in the presentation.

![model%20with%20MAPE%20at%20bottom.png](attachment:model%20with%20MAPE%20at%20bottom.png)

# Results

We found 10 zipcodes with projected high ROIs in the next two years:

75141

75150

75217

75224

75228

75233

76112

76114

76117

78758

## Navigate the Repository

[Presentation Materials](https://github.com/acollins28/Phase-4/tree/main/Phase%204%20Presentation%20Materials)

[Notebook](https://github.com/acollins28/Phase-4/blob/main/Notebook(1).ipynb)

[Presentation](https://github.com/acollins28/Phase-4/blob/main/Presentation.pptx)

[READ_ME](https://github.com/acollins28/Phase-4/blob/main/READ_ME.md)

[Data](https://github.com/acollins28/Phase-4/blob/main/zillow_data.zip)


