# nyc-citibike
nyc citibike data analysis

This repository contains testing and output of various analyses of NYC Citibike trip data.

The Readme will be updated with information on any new analysis as it is uploaded. 

**1.** Added a jupyter notebook script that will create daily trip counts for each Citibike station (4/6/2021)
The output files record daily trip starts and ends.
Output includes: date, station id, trip starts, trip ends, station name, station latitude, station longitude
The script creates a separate output file for each month.

The script presumes:
- uniformity in naming convention of the unzipped csv files (some files from 2013 and 2014 do not have the standard naming convention)
- all raw trip csv files are in the same directory. It is a fairly simple change to expand to include subdirectories
- uniformity in the date/time convention and the column placement of the station name field for trip starts and ends

**Next up:**
- add station co-ordinates to allow for geo-spatial analysis in another application (e.g. ArcGIS, QGIS, Tableau) -- Done
- add steps to concatenate the files, to create separate trip count files for each year, and to create a single daily trip count file for all time
