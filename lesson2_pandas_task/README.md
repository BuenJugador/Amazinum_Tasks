# Home task: pandas 

## Question 1

- Load the energy data from the file [Energy Indicators.xls](http://unstats.un.org/unsd/environment/excel_file_tables/2013/Energy%20Indicators.xls).
It is a list of indicators of energy supply and renewable electricity production from the United Nations for the year 2013.


- It should be put into a DataFrame with the variable name of "energy"


- Make sure to exclude the footer and header information from the datafile.


- The first two columns are unneccessary, so you should get rid of them, and you should change the column labels so that the columns are:<br>
`['Country', 'Energy Supply', 'Energy Supply per Capita', '% Renewable']`


- Convert `Energy Supply` to gigajoules (there are 1,000,000 gigajoules in a petajoule).


- For all countries which have missing data (e.g. data with `...`) make sure this is reflected as `np.NaN` values.


- Rename the following list of countries (for use in later questions):
    - `Republic of Korea`: `South Korea`,
    - `United States of America`: `United States`,
    - `United Kingdom of Great Britain and Northern Ireland`: `United Kingdom`,
    - `China, Hong Kong Special Administrative Region`: `Hong Kong`


- There are also several countries with numbers and/or parenthesis in their name. Be sure to remove these, e.g.:
    - `Bolivia (Plurinational State of)` should be `Bolivia`,
    - `Switzerland17` should be `Switzerland`.


- Next, load the GDP data from the file ["world_bank.csv"](http://data.worldbank.org/indicator/NY.GDP.MKTP.CD). 
It is a csv containing countries' GDP from 1960 to 2015 from World Bank. Call this DataFrame "GDP"


- Make sure to skip the header, and rename the following list of countries:
    - `Korea, Rep.`: `South Korea`,
    - `Iran, Islamic Rep.`: `Iran`,
    - `Hong Kong SAR, China`: `Hong Kong`


- Finally, load the "Sciamgo Journal and Country Rank data for [Energy Engineering and Power Technology"](http://www.scimagojr.com/countryrank.php?category=2102). It ranks countries based on their journal contributions in the aforementioned area. Call this DataFrame "ScimEn"


- Join the three datasets: Energy, GDP, and ScimEn into a new dataset (using the intersection of country names). Use only the 10 years (2006-2015) of GDP data and only the top 15 countries by Scimagojr 'Rank' (Rank 1 through 15).


- The index of this DataFrame should be the name of the country, and the columns should be<br>
`['Rank', 'Documents', 'Citable documents', 'Citations', 'Self-citations', 'Citations per document', 'H index', 'Energy Supply', 'Energy Supply per Capita', '% Renewable', '2006', '2007', '2008', '2009', '2010', '2011', 2012', '2013', '2014', '2015']`

Function "answer_one" should return the resulted DataFrame (20 columns and 15 entries)

## Answer the following questions in the context of only the top 15 countries by Scimagojr Rank (aka the DataFrame returned by `answer_one()`)

### Question 2
What is the average GDP over the last 10 years for each country? (exclude missing values from this calculation.)

*This function should return a Series named `avgGDP` with 15 countries and their average GDP sorted in descending order.*

```python
def answer_two():
    Top15 = answer_one()
    return "ANSWER"
```

### Question 3
By how much had the GDP changed over the 10 year span for the country with the 6th largest average GDP?

*This function should return a single number.*

```python
def answer_three():
    Top15 = answer_one()
    return "ANSWER"
```

### Question 4

Create a new column that is the ratio of Self-Citations to Total Citations. 
What is the maximum value for this new column, and what country has the highest ratio?

*This function should return a tuple with the name of the country and the ratio.*

```python
def answer_four():
    Top15 = answer_one()
    return "ANSWER"
```

### Question 5

Create a column that estimates the population using Energy Supply and Energy Supply per capita. 
What is the third most populous country according to this estimate?

*This function should return a single string value.*

```python
def answer_five():
    Top15 = answer_one()
    return "ANSWER"
```

### Question 6
Create a column that estimates the number of citable documents per person. 
What is the correlation between the number of citable documents per capita and the energy supply per capita? Use the `.corr()` method, (Pearson's correlation).

*This function should return a single number.*

```python
def answer_six():
    Top15 = answer_one()
    return "ANSWER"
```

### Question 7
Use the following dictionary to group the Countries by Continent, then create a dateframe that displays the sample size (the number of countries in each continent bin), and the sum, mean, and std deviation for the estimated population of each country.

```python
ContinentDict  = {'China':'Asia', 
                  'United States':'North America', 
                  'Japan':'Asia', 
                  'United Kingdom':'Europe', 
                  'Russian Federation':'Europe', 
                  'Canada':'North America', 
                  'Germany':'Europe', 
                  'India':'Asia',
                  'France':'Europe', 
                  'South Korea':'Asia', 
                  'Italy':'Europe', 
                  'Spain':'Europe', 
                  'Iran':'Asia',
                  'Australia':'Australia', 
                  'Brazil':'South America'}
```

*This function should return a DataFrame with index named Continent `['Asia', 'Australia', 'Europe', 'North America', 'South America']` and columns `['size', 'sum', 'mean', 'std']`*

```python
def answer_seven():
    Top15 = answer_one()
    return "ANSWER"
```