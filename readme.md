
# Python Processes #

The Python processes have the following files

| Jupyter Notebook | Description |
| ---------------- | ----------- |
| most_common_street.ipynb | Finds the most common street name with more than 10 characters. Uses a road type lookup to clean the road types while processing |
| start_date.ipynb | Find the month with the second highest number of start dates |
| year.ipynb | Finds the year with the highest percentage increase |

The data is cleaned by fixing the road types. The details are below

Data Files

| File name | Description |
| --------- | ----------- |
| premises-list-as-at-8-february-2021.csv | Downloaded from the data.nsw website |
| data.csv | Used by the dashboard, converted to UTF-8 with Excel |
| address_last_name.txt | Created manually from the output of the clean_road notebook. Contains a unique list of the last words (road type) from the addresses |
| road_types.txt | List of Australian standard road type abbreviations |
| road_types.lookup | Manually created by going through the address_last_name.txt and matching the name to the Australian standard. Used to clean the data as its processed |


## Clean Road types ##

Get a copy of the AS NZS 4819-2011 Rural and urban addressing road type standards

I couldnt find an official site to download the list so used this https://goaustraliatours.com/australia-road-types/
so some names may be missing or incorrect, but using an official list would help

Make a list of the abbreviations in road_types.txt

### Get the road types used in the files ###

Run clean_roads.ipynb Jupyter notebook to get the last word from each address and create a unique list of the names, I then saved those to a file - address_last_name.txt

### Create a road type lookup file ###

I manually went through the address_last_name.txt file, I cleaned up the apostrophes etc and created for each line the name from the file and the corresponding 
name from the road_type.txt file

eg

ROAD,RD  
ROADS,RD  
STREET,ST  
STREET),ST  

This included all names that have the wrong road type, I added the correct road type on the right. I only did this for valid road types. It also included
typing errors, for example some names had a bracket in them or other errors.

All these were added to a file called road_types.lookup

## Most common street name ##

most_common_street.ipynb  

The Program will load the data from the csv file  
Loop through all the addresses and get the street name (will also clean the road types by doing the lookup)  
Get all the street names with more than 10 characters and group them by the name and get the counts  
It will print out the most common road name

## Month of the year had the second most start dates ##

start_date.ipynb  

## Year that had the largest increase year on year (percentage wise) ##

year.ipynb  




# Dashboard #

Firstly the dataset needs to be converted to UTF-8 code in excel, hence data.csv created.


