
Repository that stores datasets used in different COVID CEID projects. Repository will be made public in near future.  
=======
The datasets in the repository were compiled by members of the CEID COVID-19 working group. The data at the top level of the repository has been formated to be used 'as-is' and is updated often. Data sets were either created from html scraping or manually entered. In the case of the automated web scraping, the raw data and scripts are organized into sub-directories. The description of each data file along with the corresponding sub-directories are listed below.   

# Automated data sets
  These data sets were created using web scraping, or other automated methods to retrieve, aggregate, and organize public data. These data sets tend to be updated nightly. 

## China data
[China_casedata](#china_casedata) </br>

## US data  
[UScases_by_state_wikipedia.csv](#uscases_by_state_wikipedia): Number of new cases in a state by day. </br>
[USfatalities_by_state_wikipedia.csv](#usfatalities_by_state_wikipedia): Number of new case fatalities in a state by day. </br>

## Global
[worldCases.csv](#worldcases): Number of new cases in a country by day. </br>

# Manual data sets
  These data sets were created by manually entering each line from various sources. 
 
longFormStateInterventions.csv : Running summary of interventions at the state level taken from reports and wikipedia

## China 
[China_TA](#china_ta): Travel advisories or restrictions within China. </br>

## US data

[interventionTimeSeries.csv](#interventiontimeseries): Reshaped version of longFormStateInterventions.csv that includes the intervention status of all US states on each date since the beginning of the outbreak. Updated daily. </br>

## Global
[China_TA](#international_ta): Travel advisories announced by county. </br>
[Epidemiological characteristics of COVID-19 and other zoonotics](#epi_characteristics)</br>

----

----

## UScases_by_state_wikipedia
Reads from wikipedia the number of non-repatriated COVID-19 cases in the US by state. Generated by `read_UScases_wikipedia.R` that extracts data from [2020 coronavirus pandemic in United States wiki page](https://en.wikipedia.org/wiki/2020_coronavirus_pandemic_in_the_United_States) and outputs file 'UScases_by_state_wikipedia.csv'.

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
- `Death_New`: Number of new death cases 
- `Death_Cml`: Cumulative number of death cases
- `Rec_New`: Number of new recoveries
- `Rec_Cml`: Cumulative number of recoveries
- `time_last_update`: day and time of last table update

<b>Related subdirectory and/or files </b>
- `read_UScases_wikipedia.R`
- UScases_by_state_wikipedia.csv

<b>Projects</b>
- TBD

## USfatalities_by_state_wikipedia
Reads from wikipedia the number of fatalities from non-repatriated COVID-19 cases in the US by state. Generated by `read_UScases_wikipedia.R` that extracts data from [2020 coronavirus pandemic in United States wiki page](https://en.wikipedia.org/wiki/2020_coronavirus_pandemic_in_the_Unite) and outputs file 'USfatalities_by_state_wikipedia.csv'.

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
- `Death_New`: Number of new death cases 
- `Death_Cml`: Cumulative number of death cases
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
 
## International_TA

This dataset contains travel restrictions enacted between China and various entities (countries, airlines, etc.) as well as other quarantines and travel restrictions enacted outside of China

<b>Metadata: </b> </br>
- city_source: city of origin where travel restriction pertains to
- ADM2_source: ADM2 name of origin where travel restriction pertains to
- ADM1_source: ADM1 name of origin where travel restriction pertains to
- country_source: country of origin where travel restriction pertains to
- country_code_source: country code of origin
- city_destination: city of destination where restriction is in place
- ADM2_destination: ADM2 name of destination where restriction is in place
- ADM1_destination: ADM1 name of destination where restriction is in place
- country_destination: name of country that enacted a travel restriction
- country_code_destination: iso2 code of country that enacted a travel restriction: https://en.wikipedia.org/wiki/ISO_3166- 1_alpha- 2
- travel_advisor: name of entity that announced travel restriction
- travel_advisor_type: type of entity that announced travel restriction (e.g. government, corporate, etc.)
- travel_restriction_date: date travel restriction put in place/announced YYYY-MM-DD format
- travel_restriction_date_end: date travel restriction lifted YYYY-MM-DD format
- strict_restrictions: does restriction include strict quarantine or travel ban? likley need to revisit this definition
- notes: description of travel restriction
- tr_source1: source url
- accessed_date1: date accessed url
- who_by1: inititials of person who accessed
- tr_source2: url of additional source
- accessed_date2: same as above
- who_by2: same as above

## China_TA

Travel advisories and restrictions implemented by the Chinese government. 

*Metadata:* 
- city:	see spatial taxonomy
- prefecture:	see spatial taxonomy
- province:	see spatial taxonomy
- travel_advisor:	Government Branch/Level/Company
- travel_restriction_date:	MM/DD/YY
- strict_restriction:	interprefecture travel is blocked
- notes:	details on type of travel restrition: full quarantine, transit regulations (spatial scale:interprefecture, interprovincial), or implementation of monitoring at entry/exit points
- tr_source:	url link to reported travel restriction
- Accessed_date:	Last date URL was accessed 
- who_by:	initials of contributor

## interventionTimeSeries

These data are scraped manually from [wikipedia entries](https://en.wikipedia.org/wiki/U.S._state_and_local_government_response_to_the_2020_coronavirus_pandemic) (housed on [this google sheet](https://docs.google.com/spreadsheets/d/1_mk1J3ElMH5EmPILcrx8s1KqHqdQYXCWroJeKTR3pV4/edit#gid=221668309)).

Google sheet is downloaded here to longFormStateInterventions.csv daily and converted into a time series of intervention intensity interventionTimeSeries.csv.

<b>Metadata:</b> 

- `NAME`: Name of state
- `DATE`: Date
- `prohibit_restaurants`: Is the state government prohibiting restaurants from opening? (0/1)
- `school_closure`: Has the government mandated that schools close or go online? (0/1)
- `state_of_emergency`: Has a state of emergency been declared? (0/1)
- `prohibit_gatherings`: Has the state government prohibited gatherings over a certain size? (0/1)
- `gathering_size`: Maximum legal gathering size in state (NA if no gathering size instituted)
- `Intervention Score`: Sum of first four metrics of intervention (0-4) 
 
 
<b>Related subdirectory and/or files</b>

<b>Projects</b>
List/Link related projects

## Epi_characteristics

Table of epidemological characteristics of COVID-19 and other zoonotic outbreaks. Data was manually entered from research articles with a PubMed publication identification number. The data set was built to capture the most about of data, so many of the cases are incomplete. The same research article could be used for multiple lines if different outbreaks or statistics were reported. 

This is a static data set.

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
<table>
  <tr>
    <th>Name</th>
    <th>Technical definition</th>
    <th>Explanation</th>
    <th>allowed values</th>
    <th></th>
  </tr>
  <tr>
    <td>R0</td>
    <td>basic reproductive number</td>
    <td>the average number of new infections that are caused by one infectious person, assuming the whole population is susceptible. This value can differ based on setting, e.g. it is likely higher in more crowded places, or can vary between children and adults.</td>
    <td>numeric</td>
    <td></td>
  </tr>
  <tr>
    <td>R0-pre</td>
    <td>R0 before symptoms occur</td>
    <td></td>
    <td>numeric</td>
    <td></td>
  </tr>
  <tr>
    <td>R0-asym</td>
    <td>R0 of asymptomatic infected</td>
    <td></td>
    <td>numeric</td>
    <td></td>
  </tr>
  <tr>
    <td>days_presymptomatic</td>
    <td>time from exposure to onset of illness (incubation period)</td>
    <td>the number of days between pathogen exposure and the onset of symptoms.</td>
    <td>numeric</td>
    <td></td>
  </tr>
  <tr>
    <td>days_symptomatic</td>
    <td>duration of symptomatic period in days</td>
    <td></td>
    <td>numeric</td>
    <td></td>
  </tr>
  <tr>
    <td>days_infectious</td>
    <td>duration of infectious period. This might or might not be the same as the symptomatic period.</td>
    <td>the number of days over which an infected individual is able to transmit the virus. This might or might not be the same as the symptomatic period.</td>
    <td>numeric</td>
    <td></td>
  </tr>
  <tr>
    <td>generation_time</td>
    <td>average time from start of infection of 1st case to infection of subsequent case</td>
    <td></td>
    <td>numeric</td>
    <td></td>
  </tr>
  <tr>
    <td>serial_interval_sym</td>
    <td>average time from start of symptoms of 1st case to symptoms of subsequent case</td>
    <td>the number of days between the onset of symptoms in one case and the onset of symptoms in a subsequent case.</td>
    <td>numeric</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_asymptomatic</td>
    <td>proportion of individuals who are asymptomatic</td>
    <td>the percent of individuals who are asymptomatic.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_symptomatic</td>
    <td>proportion of individuals who are symptomatic</td>
    <td>the percent of individuals who are symptomatic.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_inf_fever</td>
    <td>proportion infected individuals who had fever</td>
    <td>the percent of infected patients that present with a fever.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_inf_cough</td>
    <td>proportion infected individuals who had cough</td>
    <td>the percent of infected patients that present with a cough.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_sym_fever</td>
    <td>proportion symptomatic individuals who had fever</td>
    <td>the percent of symptomatic patients that present with a fever.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_sym_cough</td>
    <td>proportion symptomatic individuals who had cough</td>
    <td>the percent of symptomatic patients that present with a cough.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_inf_hospitalized</td>
    <td>proportion infected individuals who have a severe infection and require hospitalization</td>
    <td>the percent of infected patients that are hospitalized.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_inf_death</td>
    <td>proportion of infected individuals who die</td>
    <td>the percent of infected patients that die from their illness.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_hospitalized_death</td>
    <td>proportion of hospitalized cases that result in death</td>
    <td>the percent of individuals who are in severe/critical condition that die from their illness.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_sym_hospitalized</td>
    <td>proportion symptomatic individuals who have a severe infection and require hospitalization</td>
    <td>the percent of symptomatic patients that are hospitalized.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_sym_death</td>
    <td>proportion of symptomatic individuals who die</td>
    <td>the percent of symptomatic patients that die from their illness.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_infection_reduction_masks</td>
    <td>proportion by which risk of infection is reduced in susceptible individuals wearing masks</td>
    <td></td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_critical_death</td>
    <td>proportion of critical cases that result in death</td>
    <td>the percent of patients in critical condition that die from their illness.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_inf_critical</td>
    <td>proportion of infected individuals in critical condition</td>
    <td>the percent of infected patients that are in critical condition.</td>
    <td>0-1</td>
    <td></td>
  </tr>
  <tr>
    <td>prop_sym_critical</td>
    <td>proportion of symptomatic individuals in critical condition</td>
    <td>the percent of symptomatic patients that are in critical condition.</td>
    <td>0-1</td>
    <td></td>
  </tr>
</table>
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
See License.txt

Contact John Drake (jdrake@uga.edu) for questions. 

