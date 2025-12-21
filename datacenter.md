# Measuring Business Value and Productivity Data Center

## I. Adding a new dataset.

The site loads data from CSVs and dynamically builds nested list representations as follows.

### 1. Format CSV

The JavaScript function used to load the data assumes the following format:

* All variable names are listed in the first column.
* If a variable is "nested" under a variable that appears above it, it must have a greater indent.
  * Note that only the _relative_ length of the indent matters. 
* For example, a CSV containing GDP data may appear as follows:
```
"Gross Domestic Product", ...
"  Consumption",  ...
"    Goods", ...
"    Services", ...
"  Investment", ...
```
* The remaining columns each correspond to a year, with the first row in each column giving the year.

Once properly formated, add the CSV you wish to use to the DATA subdirectory.

### 2. Update datacenter.html

* Download datacenter.html and open in a code editor.
* Use `Ctrl + F` (`Cmd + F`) to locate the following line:
```
<!-- Add new datasets here -->
```
* Add the new dataset using the following template:
```
<button id="idname" class="selection-entry" onclick=
    "buildTables(
      'csvName',
      'startRow', 
      'endRow',
      headers = ['H1', 'H2'],
      'source'
    ); highlightDataset(this);"
  ><p> DatasetName </p></button>
```
where : 
* **idname** is a short string that identifies the dataset.
* **csvName** is the name of the CSV file. _Do not include the .csv extension._
* **startRow** is the text content in the first column of the first row in the CSV you wish to include in the tables.
* **endRow** is the text content in the first column of the final row in the CSV you wish to include in the tables.
  * Both **startRow** and **endRow** should have all leading and trailing whitespace removed.
* **H1** and **H2** are the variables you wish to act as headers for the two data selection tables.
* **source** gives the source of the dataset
  * E.g., _Statistics of Income_. Internal Revenue Service.
* **DatasetName** is the name of the dataset that will appear in the selection menu.

#### _Example_

Suppose you want to add data from a CSV file called pinkfloyd.csv. 
* The first variable you want to include is "The Wall", and the final variable is "   Pigs on the Wing (Part Two)".
* The variables you want to use as headers are "The Wall" and "Animals".
* The source of the dataset is "Britannia Row".
* The name of the dataset that you want to appear in the selection menu is "Pink Floyd".

Then, the proper syntax is:
```
<button id="PinkFloyd" class="selection-entry" onclick=
    "buildTables(
      'pinkfloyd',
      'The Wall', 
      'Pigs on the Wing (Part Two)',
      headers = ['The Wall', 'Animals'],
      'Britannia Row'
    ); highlightDataset(this);"
  ><p> Pink Floyd </p></button>
```

Once finished, upload the updated datacenter.html to this repository.

---

## II. Editing the site
