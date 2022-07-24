Firstly the dataset need to convert to UTF-8 code in excel, hence data.csv created.

# Clean Road types #

Get a copy of the AS NZS 4819-2011 Rural and urban addressing road type standards

I couldnt find an official site to download the list so used this https://goaustraliatours.com/australia-road-types/
so some names may be missing or incorrect, but using an official list would help

Make a list of the abbreviations in road_types.txt

## Get the road types used in the files ##

Run clean_roads.ipynb Jupyter notebook to get the last word from each address and create a unique list of the names, I then saved those to a file - address_last_name.txt

## Create a road type lookup file ##

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

# Run the Jupyter notebook to get the most common road name #

The Program will load the data from the csv file  
Loop through all the addresses and get the street name (will also clean the road types by doing the lookup)  
Get all the street names with more than 10 characters and group them by the name and get the counts  
It will print out the most common road name


