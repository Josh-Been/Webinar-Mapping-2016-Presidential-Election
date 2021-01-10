<a href="https://www.tdl.org/event/tdl-gisig-webinar-hands-on-tableau-desktop-mapping-the-2016-presidential-election/"><img src="https://www.tdl.org/wp-content/uploads/2020/09/GIS-webinars_V2-768x432.png" width=500></a>

[ReadMe URL](https://josh-been.github.io/Webinar-Mapping-2016-Presidential-Election-Using-Tableau-Desktop/)

# Webinar Description

**Date/Time**: January 12, 11am

**Title**: Hands-On Tableau Desktop: Mapping the 2016 Presidential Election

**Description**: Participants of this introductory webinar will gain hands-on experience generating interactive maps and map-centric dashboards using Tableau Desktop. The content we will focus on during this webinar will be 2016 Presidential election results by voter tabulation district in Texas and Census data from the American Community Survey. (Unfortunately, it is too early to obtain 2020 results by VTD. Stayed tuned for future mapping workshops when 2020 data is released.)
 - Click to Explore Finished Product
 - <a href="https://public.tableau.com/views/TDLGISIGDashboard-Mapping2016Election/Dashboard1?:embed=y&:display_count=no&:showVizHome=no#1" target="_blank"><img src="https://i.ibb.co/PNnncYT/tdlgispreview.png" width=500></a>

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

## Step #2: Visualize Census Data

1. Load demographics.xlsx File into Tableau Desktop
 - Launch Tableau (*can be either Tableau Public or Professional*)
 - Click *Connect/To a File/Microsoft Excel* and browse to the demographics.xlsx file.
 - Click the orange *Sheet 1* button
2. Create Treemap Visualization Showing Income by County
 - Select County under Dimensions
 - Hold CTRL and select Income under Measures
 - Under Show Me on the right, click TreeMap
3. This is not correct, is it? Let's correct the aggregation.
 - Click the Undo button at the top left of the screen
 - Right-click Income, under Measures, and select Deafult Properties/Aggregation/Average
 - Now recreate Treemap
3. Change Visualization to Packed Bubbles
 - Click the Packed Bubbles button on the Show Me tab
 - Drag Income under Measures to the Color box
 - Click the Color box and then click Edit Colors to adjust the color scheme.
4. Change Visualization to Highlight Table
 - Click the *Highlight Table* icon on the Show Me tab
 - Click the *Descending* button on the top toolbar.
5. Rename and Duplicate Sheet 1
 - Right-click *Sheet 1* and select *Rename*
 - Raname to *Highlight Table*
 - Right-click *Highlight Table* and select *Duplicate*
 - Rename the new sheet County Map
6. Change Visualization to County Map (*finally, right?*)
 - Change visualization to Map (polygons)
 - Click the Map button on the Show Me tab
 - Click the 99 Unknown tag that appears on the bottom right of the map
 - Select *Edit Locations*
 - Under State/Province, select Fixed and then Texas.
 - OK
7. Change map colors from Income to % Hispanic
 - Don't forget to change aggregation to *Average*!
8. Adjust Basemap Layers
 - On the top toolbar, click Map and then *Map Layers*
 - Style can be adjusted
 - Individual layers can be adjusted within any style

## Step #3: Integrate Election Data

1. Load Pres2016.xlsx File
 - Explore the pres2016.xlsx table using Excel. 
 - Click Data Source on the bottom left of the screen
 - Click the blue Add button and click Microsoft Excel
 - Select the pres2016.xlsx file
 - Drag *presidential* to the window next to *demographics*. This should automatically connect to the *demographics* table and the Edit Relationship window will appear.
 - The default Cntyvtd will connect to the Cntyvtd1 column.
 - Click the *County Map* tab
 - Now both tables are available.
2. View % Votes for Trump in 2016 by County
 - Aggregation fix is necessary again!
 - Drag *Trump* to Color Box.

## Step #4: Integrate VTD Boundaries

1. Load VTDs.shp Shapefile
 - Click Data Source on the bottom left of the screen
 - Click the blue Add button and click Spatial file
 - Browse and select the VTDs.shp shapefile
 - Drag *VTDs* to the window next to *demographics*.
 - The default relationship is perfect
2. Create a New Sheet
 - Rename the New Sheet *VTD Map*
3. Map Data Using VTD Boundaries
 - In the Table of Contents on the left, double-click *Geometry* under VTDs.
 - Drag CNTYVTD to the Detail Box
 - Drag % Votes for Clinton to the Color Box
4. Remove polygon booundaries to view urban VTDs
 - Click the Color Box
 - Change *Border* to *None*
5. Add Filter for County
 - Right-click *County* under the demographics table and select *Show Filter*
 - Hide the Show Me tab if visible
 - Under the County filter options, select *Multiple Values Dropdown*

## OPTIONAL Step #5: Dynamic Dropdown to Adjust Color
1. Create a new *Parameter* to hold color background choices
 - Name the Parameter Choose Variable
 - Data Type: String
 - Allowable Values: List
 - Under List of Values, enter *Income*, *% Clinton*, *% Trump*
 - OK
 - From the new *Parameters* list on the bottom left, right-click Choose Variable and click *Show Parameter*
2. Create a new *Calculated Field* to hold values of selection
 - Name the Calculated Field *Variable Placeholder*
 - Formula:
      <blockquote>
      IF [Choose Variable]="Income" THEN [Income]<br>
      ELSEIF [Choose Variable]="% Clinton" THEN [Clinton]<br>
      ELSEIF [Choose Variable]="% Trump" THEN [Trump]<br>
      END
      </blockquote>
3. Drag Variable Placeholder to the Color Box
4. Nice, huh?
5. Navigate to the *Highlight Table* sheet
 - Set default aggregation for *Variable Placeholder* to Average
 - Drag *Value Placeholder* to the Color Box
5. Navigate to the *County Map*
 - Drag *Value Placeholder* to the Color Box

## Step #6: Create & Publish Dashboard
1. Set the Page Size
 - Click the *New Dashboard* icon
 - Under *Size* click the size suggested
 - Change *Fixed* to *Automatic*
2. Drag Sheets to arrange as you see fit
3. Set the *County* filter to Apply to Worksheets/All
4. **Publish Steps - If Using Tableau Professional**
 - CLick Data/demographics/Extract Data
 - Click Extract
 - Click Server/Tableau Public/Save to Tableau Public
5. **Publish Steps - If Using Tableau Public**
 - Click File/Save to Tableau Pubic
