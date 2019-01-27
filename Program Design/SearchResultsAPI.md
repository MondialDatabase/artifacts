# Input Parameters

## Required

* countryName: String

## Optional

* population: Boolean (default value: False)
* area: Boolean (default value: False)
* infantMortality: Boolean (default value: False)
* populationGrowthRate: Boolean (default value: False)
* government: Boolean (default value: False)
* independenceData: Boolean (default value: False)
* gdpInMillionsUsd: Boolean (default value: False)
* agriculatureAsPercentOfGdp: Boolean (default value: False)
* serviceAsPercentOfGdp: Boolean (default value: False)
* industryAsPercentOfGdp: Boolean (default value: False)
* inflateRatePerAnnum: Boolean (default value: False)
* totalLengthOfBorder: Boolean (default value: False)
* capital: Boolean (default value: False)
* languageData: Boolean (default value: False)
* religionData: Boolean (default value: False)
* ethnicityData: Boolean (default value: False)
* borderingCountryData: Boolean (default value: False)
* continentData: Boolean (default value: False)
* cityData: Boolean (default value: False)
* mountainData: Boolean (default value: False)
* seaData: Boolean (default value: False)
* riverData: Boolean (default value: False)
* islandData: Boolean (default value: False)
* lakeData: Boolean (default value: False)
* desertData: Boolean (default value: False)

# Output

## Required

* countryName: String

## Optional

* population: Number
* area: Number
* infantMortality: Number
* populationGrowthRate: Number
* government: String
* independenceData: String
* gdpInMillionsUsd: Number
* agricultureAsPercentOfGdp: Number
* serviceAsPercentOfGdp: Number
* industryAsPercentOfGdp: Number
* inflationRatePerAnnum: Number
* totalLengthOfBorder: Number
* capital: String
* languageData: List<CountryDatum>
* religionData: List<CountryDatum>
* ethnicityData: List<CountryDatum>
* borderingCountryData: List<CountryDatum>
* continentData: List<String>
* cityData: List<String>
* mountainData: List<String>
* seaData: List<String>
* riverData: List<String>
* islandData: List<String>
* lakeData: List<String>
* desertData: List<String>

# Data Types

* CountryDatum:
  * ColumnName: String
  * ColumnValue: Number

# Primary Database Tables

* Country
* Population
* Politics
* Economy
* Borders
* Language
* Religion
* EthnicGroup
* Continent
* City
* Mountain
* Sea
* River
* Island
* Lake
* Desert

# Relational Database Tables

* Encompasses
* Geo_Mountain
* Geo_Sea
* Geo_River
* Geo_Island
* Geo_Lake
* Geo_Desert

# Algorithm

1. Build an initial query string that selects one country name from the Country database table with a name equivalent to the countryName input parameter.
2. If population input parameter is true, append a selection for country population to the query.
3. If area input parameter is true, append a selection for country area to the query.
4. If infantMortality input parameter and/or populationGrowthRate input parameter is true, join country table selection query with the Population table on the Country column.
5. If government input parameter and/or the independenceData input parameter is true, join country table selection query with the Politics table on the Country column.
6. If gpdInMillionsUsd, agricultureAsPercentOfGdp, serviceAsPercentOfGdp, industryAsPercentOfGdp, and/or inflationRatePerAnnum input parameter is true, join country table selection query with the Economy table on the Country column.
7. If totalLengthOfBorder and/or borderingCountryData input parameter is true, join country table selection query with the Borders table on the Country1 column (and/or Country2?)
8. If capital input parameter is true, append a selection for country capital to the query.
9. If languageData input parameter is true, join country table selection query with the Language table on the Country column.
10. If religionData input parameter is true, join country table selection query with the Religion table on the Country column.
11. If ethnicityData input parameter is true, join country table selection query with the EthnicGroup table on the Country column.
12. If continentData input parameter is true, join country table selection query with the Encompasses table on Country column then join the Encompasses table with the Continent table on the Name column.
13. If cityData input parameter is true, join country table selection query with the City table on the Country column.
14. If mountainData input parameter is true, join country table selection query with the Geo_Mountain table on the Country and Province columns then join the Geo_Mountain table with the Mountain table on the Name column.
15. If seaData input parameter is true, join country table selection with the Geo_Sea table on the Country and Province columns then join the Geo_Sea table with the Sea table on the Name column.
16. If riverData input parameter is true, join country table selection with the Geo_River table on the Country and Province columns then join the Geo_River table with the River table on the Name column.
17. If islandData input parameter is true, join country table selection with the Geo_Island table on the Country and Province columns then join the Geo_Island table with the Island table on the Name column.
18. If lakeData input parameter is true, join country table selection with the Geo_Lake table on the Country and Province columns then join the Geo_Lake table with the Lake table on the Name column.
19. If desertData input parameter is true, join country table selection with the Geo_Desert table on the Country and Province columns then join the Geo_Desert table with the Desert table on the Name column.
20. Perform the database query and store the results in a variable.
21. Return only the result properties that were requested via the input parameters to the caller.
