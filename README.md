<a href="https://www.tdl.org/event/tdl-gisig-webinar-hands-on-tableau-desktop-mapping-the-2016-presidential-election/"><img src="https://www.tdl.org/wp-content/uploads/2020/09/GIS-webinars_V2-768x432.png" width=500></a>

[ReadMe URL](https://josh-been.github.io/Webinar-Mapping-2016-Presidential-Election-Using-Tableau-Desktop/)

# Webinar Description

**Date/Time**: January 12, 11am

**Title**: Hands-On Tableau Desktop: Mapping the 2016 Presidential Election

**Description**: Participants of this introductory webinar will gain hands-on experience generating interactive maps and map-centric dashboards using Tableau Desktop. The content we will focus on during this webinar will be 2016 Presidential election results by voter tabulation district in Texas and Census data from the American Community Survey. (Unfortunately, it is too early to obtain 2020 results by VTD. Stayed tuned for future mapping workshops when 2020 data is released.)

**Participation**: Participants can follow along or sit back and watch. To follow along, please install Tableau Desktop prior to the webinar starting.

**Presenters**:
 - [Joshua Been, Baylor University](https://www.baylor.edu/library/index.php?id=969726)
 - [Kristina Claunch, Sam Houston State University](https://shsulibraryguides.org/prf.php?account_id=249033)

# Tableau Software

**Tableau Desktop Software Options** Either Tableau Desktop Public (freely available) or Tableau Desktop Professional (fee-based, free to students and teachers) will work perfectly for this webinar.
1. [Tableau Desktop Public](https://public.tableau.com/en-us/s/)
2. [Tableau Desktop Professional (student license)](https://www.tableau.com/academic/students)
3. [Tableau Desktop Professional (teacher license)](https://www.tableau.com/academic/teaching)

# Webinar Data

[Zip Archive of All 3 Files](https://baylor0-my.sharepoint.com/:u:/g/personal/joshua_been_baylor_edu/ESl_zYE_vJVLghLNpaZOAdMBRsvNRz3vkNyj3hn7Ugv3hA?download=1)

*Data from Texas Legislative Council*
1. [Texas Voter Tabulation District (VTD) Shapefile](https://data.capitol.texas.gov/dataset/vtds)
2. [2016 General Election Data](https://data.capitol.texas.gov/dataset/2016_general) - The election data included in the *zip archive* has been pre-processed. The complete 2016 election data was filtered and pivoted for Presidential votes and then percent votes were calculated for each candidate.

*Data from U.S. Census*

3. [Census American Community Survey](https://data.census.gov/cedsci/) - This Census data included in the *zip archive* has been pre-processed. Data was downloaded for Census Block Groups and approximated to VTD polygons using an area-weighted spatial join approach using ArcGIS.

# Webinar Steps

## Step #1: Explore 3 Prepared Datasets
1. Download [Zip Archive of All 3 Files](https://baylor0-my.sharepoint.com/:u:/g/personal/joshua_been_baylor_edu/ESl_zYE_vJVLghLNpaZOAdMBRsvNRz3vkNyj3hn7Ugv3hA?download=1)
2. Unzip the contents [help unzipping](https://www.wikihow.com/Unzip-a-File)
3. Explore (preview) the demographics.xlsx file using Excel.

## Step #2: Load demographics.xlsx File into Tableau Desktop
1. Launch Tableau (*can be either Tableau Public or Professional*)
2. Click *Connect/To a File/Microsoft Excel* and browse to the demographics.xlsx file.
3. Click the orange Sheet 1 button

## Step #3: Create Treemap Visualization Showing Income by County
1.	Select County under Dimensions
2.	Hold CTRL and select Income under Measures
3.	Under Show Me on the right, click TreeMap
4. This is not correct, is it? Let's correct the aggregation.
    - Click the Undo button at the top left of the screen
    - Right-click Income, under Measures, and select Deafult Properties/Aggregation/Average
    - Now recreate Treemap

## Step #4: Change Visualizations
1. Packed Bubbles
    - Click the Packed Bubbles button on the Show Me tab
    - Drag Income under Measures to the Color box
    - Click the Color box and then click Edit Colors to adjust the color scheme.
2. County Map (*finally, right?*)
    - Change visualization to Map
    - Click the Map button on the Show Me tab
    - Click the 99 Unknown tag that appears on the bottom right of the map
    - Under State/Province, select Fixed and then Texas.
    - OK

## Step #5: Load Pres2016.xlsx File
1. Explore the pres2016.xlsx table using Excel. 
2. Click Data Source on the bottom left of the screen
3. Click the blue Add button and click Microsoft Excel
4. Select the pres2016.xlsx file
5. Drag *presidential* to the window next to *demographics*. This should automatically connect to the *demographics* table and the Edit Relationship window will appear.
6. The default Cntyvtd will connect to the Cntyvtd1 column.
7. Close the Edit Relationship window and click Sheet 1. Now both tables are available.

## Step #6: View % Votes for Trump in 2016 by County
1. Drag Trump to the Color box
2. Aggregation fix is necessary again!

## Step #7: Load VTD Shapefile
1. Click Data Source on the bottom left of the screen
2. Click the blue Add button and click Spatial file
3. Browse and select the VTDs.shp shapefile
4. Drag *VTDs* to the window next to *demographics*.
5. The default relationship is perfect
6. Back to Sheet 1

## Step #8: Map Data Using VTD Boundaries
1. 
