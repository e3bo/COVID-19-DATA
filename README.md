
Repository that stores datasets used in different COVID CEID projects. Repository will be made public in near future.  
=======
The datasets in the repository were compiled by members of the CEID COVID-19 working group. The data at the top level of the repository has been formated to be used 'as-is' and is updated often. Raw data and scripts are organized into sub-directories. The description of each data file along with the corresponding sub-directories are listed below.   

# Compiled data sets

[UScases_by_state_wikipedia.csv](#uscases_by_state_wikipedia) </br>
[worldCases.csv](#worldcases) </br>
[China_casedata](#china_casedata) </br>
[Epidemiological characteristics of COVID-19 and other zoonotics](#epi_characteristics)</br>

## UScases_by_state_wikipedia
Reads from wikipedia the number of non-repatriated COVID-19 cases in the US by state. Generated by `read_UScases_wikipedia.R` which extracts data from [2020 coronavirus pandemic in United States wiki page](https://en.wikipedia.org/wiki/2020_coronavirus_pandemic_in_the_United_States) and outputs file 'UScases_by_state_wikipedia.csv'.

<b>Metadata: </b> </br>
 Column name description of data file:
- `Date` - Date correspondent to the number of cases
- Columns 2-14: Western US states
- Columns 15-27: Midwestern US states
- Columns 28-39: Southern US states
- Columns 40-51: Northeastern US states
- Column 52: GU: Guam, U.S territory
- Column 53: PR: Puerto Rico, U.S territory
- Column 54: VI: United States Virgin Islands, U.S territory
- `Conf_New`: Number of new confirmed cases 
- `Conf_Cml`: Cumulative number of confirmed cases
- `Death_New`: Number of new deaths
- `Death_Cml`: Cumulative number of deaths
- `Rec_New`: Number of new recoveries
- `Rec_Cml`: Cumulative number of recoveries
- `time_last_update`: day and time of last table update

<b>Related subdirectory and/or files </b>
- `read_UScases_wikipedia.R`
- UScases_by_state_wikipedia.csv

<b>Projects</b>
- TBD

## worldCases
Stores data read from wikipedia on the cumulative number of cases in a country. Added to each day by running `get-world-data.Rmd`to
extract data from [2020 coronavirus pandemic wiki page](https://en.wikipedia.org/wiki/2019%E2%80%9320_coronavirus_pandemic) and adds the current day to the dataset. Must be run every day at ~10 PM or extracted from archived pages on wayback machine. Wikipedia does not store these data by date so running daily at the same time is necessary to keep data current and accurate.

<b>Metadata:</b> </br>
 Column name description of data file:
 - `Date`: Date of cumulative case record
 - `Country`: Country name
 - `Cases`: cumulative number of cases for `Country` on `Date`

<b>Related subdirectory and/or files</b>
- `get-world-data.Rmd`
- worldCases.csv

<b>Projects</b>
- TBD

## China_casedata
Here is some discription

<b>Metadata:</b> 


<b>Related subdirectory and/or files</b>
- [China_casedata](https://github.com/CEIDatUGA/COVID-19-DATA/tree/master/China_casedata)

<b>Projects</b>
 - [Early Intervention](https://github.com/CEIDatUGA/ncov-early-intervention)
 - [Spatial spread in China](https://github.com/CEIDatUGA/CoronavirusSpatial)

## Epi_characteristics
<b>Metadata:</b> 
 Column name: Description, [Allowed Values] 
 - pathogenName:	Name of pathogen	[2019-nCoV, SARS-CoV, MERS-CoV, H1N1 virus, H5N1 virus, Ebola virus]
 - outbreak:	Specify disease outbreak	[e.g. 2003 global SARS outbreak, 2014-2016 West Africa Ebola virus disease outbreak]
 - parameter:	the quantity reported.[ one of several allowed values. see "Parameter Explanations" below for details.]	
 - estimate:	value of the main reported estimate in the provided source. If more than one estimate is reported, add it as separate line item.	[numeric]
 - censored:	indicate if a value is left- or right- censored or not. E.g. if a paper reports "at least >20 days"/"less than 10" it would be right/left censored. Instead of writing >20 in the estimate column, write 20 into estimate and indicate that it's right censored.[	L, R, N]
- estimateUnit:	unit of the value reported in the estimate column [text]
- estimateType:	type of estimate, if reported.	[mean, median, mode]
- lowerBound:	if reported, lower bound of uncertainty interval	[numeric]
- upperBound:	if reported, upper bound of uncertainty interval	[numeric]
- intervalKind:	type of uncertainty interval, if reported.	[95% confidence interval, 90% credible interval, interquartile range, range]
- ageMean:	mean age of population in question (if reported)	[numeric]
- ageMedian:	median age of population in question (if reported)	[numeric]
- ageMin:	min age of population in question (if reported)	[numeric]
- ageMax:	max age of population in question (if reported)	[numeric]
- proportionMale:	proportion of males of population in question (if reported)	[0-1]
- country:	country where data came from	[text]
- continent:	continent where data came from. Not needed if country is provided.	[text]
- entryAuthor:	person who added the entry to the spreadsheet	[text]
- checkedby:	name of person who checked a given entry	[text]
- publicationFirstAuthor:	last name of 1st author of publication	[text]
- publicationYear:	year the paper was published. NOT year of data collection.	[numeric]
- PMID:	Pubmed ID	[valid PMID]
- URL: URL to paper	[URL (ideally DOI)]
- title:	title of reference/paper	[text]
- notes:	any comments worth being aware of	[text]

<b>Parameter Explanations</b>

<b>Related subdirectory and/or files</b>

<b>Projects</b>
List/Link related projects



## Data_name
Here is some discription of how the data is collected, when it is normally updated, etc. 

<b>Metadata:</b> 
 
 
<b>Related subdirectory and/or files</b>

<b>Projects</b>
List/Link related projects
# License 
TBD

Contact John Drake (jdrake@uga.edu) for questions. 

