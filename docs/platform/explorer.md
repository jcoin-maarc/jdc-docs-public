# Exploration Page

The exploration page enables the user to explore the data common's harmonized data as well as files through dynamic filters and marginal distribution charts. 

Note, the exploration page only shows data and files the user has been granted access.
## General exploration features

### Tables
 Tables at the bottom of the tab show a subset of variables for individual records' of the selected properties. 
### Total counts
A total count is displayed in the middle of the page. It represents the total count of either files or harmonized data records after accounting for access privileges and filters. 
### Charts
The charts, on the tab dashboard's right side, display marginal distributions (e.g., count and/or percentage) of a variable (i.e., field, property etc) in the data. This provides a quick breakdown of the harmonized data for a selected cohort. Additionally, for file tabs, a similar breakdown from a specified set of file metadata fields (made possible by mapping uploaded files to these metadata fields).

There are several types of these charts:

<!-- Add figures with figure captions -->
Full pie chart
Bar chart
Stack bar chart
### Filters 

The left side of each dashboard tab contains variables to filter on (e.g., sliders for numeric variables,checkboxes for variables with a set of possible values, or a search bar for a categorical variable). For checkbox filters, directly to right of each checkbox contains a number representing the count of records for the currently selected data. When no filters are applied, this represent all the accessible data given a user's access privileges. 

### Export data buttons

The "Export Clinical Data" button serves to directly download structured data from data tabs. 

Two file export button functionalities serve to download files. The "Export to workspace" function serves to mount data to the user's workspace ([see here for a workspace guide on the platform](workspaces.md)). The "export to manifest" button provides the metadata to give to the [gen3 client](downloading_file.md) to download the selected files.

## Participants (staff and clients) Tab

Contains data on the person level (1 observation=1 person) with marginal distributions for key variables that are a part of the quarterly report.

## Time points (clients only) Tab

Contains data on the time point level (1 observation=1 time point) with a marginal distribution of visit type.

## Files - All Tab

This tab contains a way to search and download files a user has access to. A user can search by type of file or by study.

### Total file count

It represents the total count of either files or harmonized data records after accounting for access privileges and filters. 

<!-- ### Filters

### Export files

### File Information Page -->

## Files - OEPS Tab

This contains files from the OEPS data warehouse. It is searchable by dimensions as defined by the OEPS team (e.g., "construct," "spatial dimension," and "variable")

<!-- ### Total file count

### Filters

### Export files

### File Information Page -->