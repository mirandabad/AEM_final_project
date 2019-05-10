**Census 2020: Hard to Count Communities** - AEM Final Project
---  

**Research Question:**    
What relationship (i.e., correlation) do demographic factors (e.g., race, ethnicity) have to 2010 Census response rates in Hard To Count Communities?  

*Hypothesis*: Response rates will have a positive correlation with white communities and a negative correlation with populations of color.  


**Data Sources**
The data source used is from the  [Census 2020 HTC Map Application](https://www.censushardtocountmaps2020.us/). This application was created by the [Center for Urban Research at the City University of New York Graduate Center's Mapping Service](https://www.gc.cuny.edu/urbanresearchmaps).  

The [Texas Excel File](https://www.censushardtocountmaps2020.us/exports/pdb2015tract_2010MRR_2017ACS_TX.xlsx) includes the [2010 Census mail return rate] from the US Census Bureau (), the [ACS 2013-2017 population estimates](https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml?refresh=t) for populations at risk of being undercounted, and [internet access estimates for each Census tract in Texas](https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml?refresh=t).  

> - *Notes:*  
>- The above data set has been downloaded and saved with its original file name "pdb2015tract_2010MRR_2017ACS_TX.xlsx"*    
> - The tract data is compiled from two Census Bureau sources: the Bureau's Planning Database (which provides the 2010 mail return rates); and the 2013-2017 American Community Survey estimates (via American FactFinder). The link to the Planning Database no longer works.  

The TX Excel file has two worksheets:  
one (titled "pdb2015tract_2010data_ACS17_TX") with Census Bureau data and a second (titled "Fieldnames") with a description of source information and names for columns/fields.  

> -  Since the population estimate data is an estimate, there is an margin of error. Additionally, "that state totals do not reflect the sum for all counties in Texas and are aggregated from congressional district data" (via Census 2020 HTC site).  


**Operationalization**
Since we only need to compare a few variables and are most interested in the demographic information for race and ethnicity inn Texas,  we will utilize the categorical variables from the ACS 2013-2017 Total Population Estimates (from *FIELDNAMES* tab on "pdb2015tract_2010MRR_2017ACS_TX.xlsx" sheet) for Texas Census Tracts below:  
>-	**TotPopACS17** – 2013-2017 ACS total population estimate  
>-	**WhiteAloneOrCombo** – White alone or in combination with one or more other races (ACS 2013-2017 table B02009)  
>-	**BlackAloneOrCombo** – Black or African American alone or in combination with one or more other races (ACS 2013-2017 table B02009)  
>-	**AmerIndAloneOrCombo** – People who are American Indian or Alaska Native alone or in combination with one or more other races (ACS 2013-2017 table B02010)  
>-	**AsianAloneOrCombo** – Asian alone or in combination with one or more other races (ACS 2013-2017 table B02011)  
>-	**Hispanic** – Hispanic population* (ACS 2013-2017 table B03002)  
>>-	*Census Bureau site refers to this table as “Hispanic or Latino origin by race”*  
>-	**NatHawAloneOrCombo** – Native Hawaiian and Other Pacific Islander alone or in combination with one or more other races (ACS 2013-2017 table B02012)  


**Importing Data**
Import first sheet from TX excel file (i.e., sheet named "pdb2015tract_2010data_ACS17_TX") using pandas. Filter out Census tracts not defined as hard to count communities (i.e., 2010 mail-in response rate is greater than 73%).  


**Plot for Data Analysis**
Create a scatterplot for the independent and dependent variables. After plotting each variable, we can run a linear regression to see their relationship.  


**Replication and Validation**
The accurcacy of the graphs above was in question, so an attempt to replicate and validate the data source in STATA occured. The TX excel file was imported into STATA using the "import" command, then used the "summarize", "correlate", "regress", and "scatter" commands to compare the independent and dependent variables. The non-HTC tracts were again filterd out, matching the number of observations (i.e., tracts classified as hard to count communities) in the Python code.  


**Limitations**  
Bias in Census Data Collection  
>- The Census is subject to nonresponse and sample bias  representation when attempting to find trends and information about undercounted communities
>- Bias also exists in the structure of questions, particularly with those that are socially constructed

Challenge of Validating Census Data  
>- The ACS population estimates are in fact based on estimates, which leaves room for a margin of error that will need to be accounted for.  

Challenge of Replicating Census Data  
>- The Census Bureau site had a lot of broken web links, which made accessing data challenging. They also will be moving data from American FactFinder to a new webpage, which will result in more issues finding datasets that have been hyperlinked.  


**Conclusion**
Question: What relationship (i.e., correlation) do demographic factors (e.g., race, ethnicity) have to 2010 Census response rates in Hard To Count Communities?  

Answer: The variables for race and ethnicity did not appear to be significant when compared to response rate in STATA. Additionally, the only variables that appeared to show a correlation with response rate where for respondents who were white alone or a combination or Latinx (i.e., Hispanic or Latino).  
