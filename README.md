# nyc-citibike
nyc citibike data analysis

This repository contains testing and output of various analyses of NYC Citibike trip data.

The Readme will be updated with information on any new analysis as it is uploaded. 

**1.** Added a jupyter notebook script that will create daily trip counts for each Citibike station (4/6/2021)

File name is: nyc_citibike_daily_trip_aggregator.ipynb

The output files record daily trip starts and ends.
Output includes: date, station id, trip starts, trip ends, station name, station latitude, station longitude.
The script creates a separate output file for each month.
Added a df.dropna() step in order to remove rows where the station id/station name are recorded as "NULL".

The script presumes:
- uniformity in naming convention of the unzipped csv files (some files from 2013 and 2014 do not have the standard naming convention).
- all raw trip csv files are in the same directory. It is a fairly simple change to expand to include subdirectories.
- uniformity in the date/time convention and the column placement of fields.

**2.** Added a jupyter notebook script that will create a list of stations using the daily trip count files (4/12/2021)

File name is: nyc_citibike_station_list.ipynb

The output file will contain a list of stations using the trip count files from 2018-2021.
Output includes: station id, station name, station latitude, station longitude.
This notebook requires the daily trip count files in order to run.

**3.** Added a jupyter notebook script that will create a list of stations using the daily trip count files with county included (4/13/2021)

File name is: nyc_citibike_station_list_county_update.ipynb

Output includes: station id, station name, station latitude, station longitude, county name.
This notebook requires the station list in order to run.

Added an if/except to catch/skip IndexError as there are two stations that have trips attributed to them with coordinates that fall outside the US. 
These two stations are both located on a block in Montreal - this may be a Citibike bike/station manufacture/testing site?
It's not clear why these trips appear in the raw NYC Citibike trip files.

The output file is the output from "2" with a column for county name added.

**Next up:**
- for "1", add station co-ordinates to allow for geo-spatial analysis in another application (e.g. ArcGIS, QGIS, Tableau) -- Done
- add steps to concatenate the files, to create separate trip count files for each year, and to create a single daily trip count file for all time
- add steps to "2" that will add borough code to the station file; this will permit the aggregation of trip starts, trip ends, trip totals by borough -- Done
- add steps to "3" that will add neighborhood/council district information to the fil; this will permit the aggregation of trip starts/ends and analysis of trips at a more granular neighborhood level
