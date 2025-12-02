# Measuring Business Value and Productivity Beta Site

Below are instructions to _update_ the contents of the site. For instructions on using the site, consult [the introduction included in the site](https://isaiahdal.github.io/).

## Setup

Install the following software and packages:

* [Julia](https://julialang.org/)

* [Pluto.jl](https://plutojl.org/)

* [VSCode](https://code.visualstudio.com/)

  * You may also use another code editor with support for Julia and HTML/CSS/JS. However, this guide assumes that you are using VSCode.

## Adding a New Page

> **IMPORTANT**: When adding or editing pages, see [style.md](https://github.com/IsaiahDal/isaiahdal.github.io/blob/main/style.md) for some basic coding and style standards.

#### 1. Open Pluto's Code Editor

* Open the Julia REPL by entering `julia` into your terminal.
* Paste the following line into the Julia REPL to open Pluto's code editor:

```
using Pluto; Pluto.run()
```

A tab similar to the one pictured below should open in your browser:

![PlutoWelcome](images/PlutoWelcome.png)

#### 2. Create a New Notebook

Click "+ _Create a **new notebook**_, which will open the following in a new tab:

![PlutoBlank](images/PlutoBlank.png)

#### 3. Add to the Notebook

##### a. Add New Cells

* Place your cursor over the cell immediately above or below where you wish to add the new cell.
  * Click the "Add cell" (+) button that appears to the top left of the cell to add the new cell above the current cell.
  * Click the button that appears to the bootom left of the cell to add the new cell below the current cell.
    * You can also use `CTRL + Enter` (or `CMD + enter`) to add a cell below the current cell.
   
* Pluto allows you to divide code into separate cells.
  * The two most important types of code cells are:
    * **Julia** cells, which contain the executable code of the notebook.
    * **Markdown** cells, which are used to annotate the Julia code.
 
###### i. Julia Cells

* Each code cell is assumed to be written in Julia by default.
* All cells of more than one line must be wrapped in a single code block, such as a `function` or a `begin`-`end` block.
* Cells are run in sequential order.

###### ii. Markdown Cells

* Pluto also supports Markdown cells, which use the following syntax:

```
md"""
Your markdown text here
"""
```

* Within these cells, you can use all formatting options available in traditional .md files.
* Pluto Markdown cells natively support $LaTeX$, which allows you to format mathematical expressions

##### b. Deleting Cells

* Hover your cursor over the cell you wish to delete, and click the "Actions" button that appears in the top right of the cell
* Select "Delete cell"

##### c. Toggling Cell Visibility

* Hover your cursor over the cell you wish to toggle
* Click the "Show/hide code" (👁) button that appears to the left of the cell to toggle visibility.
  * When a code cell is hidden, the cell's output remains visible. Only the code itself is hidden.
  * The visibility status of each cell is preserved when exporting to HTML in step 4.

> **NOTE**: The above is meant only as a brief introduction to using Pluto notebooks. For a more thorough tutorial of Pluto, visit its [official documentation](https://plutojl.org/en/docs/).

#### 4. Export to HTML


#### 5. Upload Files to GitHub

---

## Editing an Existing Page

> **IMPORTANT**: When adding or editing pages, see [style.md](https://github.com/IsaiahDal/isaiahdal.github.io/blob/main/style.md) for some basic coding and style standards.

### 1. Export Pluto.jl Notebook to HTML

> Make sure that all code (including Markdown) that you do not wish to display is hidden before exporting by clicking the _Show/hide code_ (👁) button located near the top left of each code cell.

Click the export button located at the top right of the Pluto.jl notebook (see below). Select **Static HTML**, then **Download HTML File**. Note that the downloaded HTML file will have the same name as the corresponding .jl file. Once exported, upload the HTML file to the notebook subdirectory of this repository.

![Export](images/exportbutton.jpg)

### 2. Update index.html

The following example assumes that the file you wish to add is named _keynes.html_ and has the title "In the long run, we are all dead".

Open index.html in your code editor. Find the toc (Table of Contents) div, which can be done by using `Ctrl (or Cmd) + F` and entering _Add new HTML page buttons here_. Add a button for the new HTML file **in the location that you wish it to appear in the table of contents**. Use the following syntax:

```
<button id="keynes" class="toc-entry">In the long run, we are all dead</button>
```

### 3. Upload Data

Upload any _new_ data files to the "DATA" subdirectory.

## Files

### index.html

The main HTML page. Used to display and navigate between the HTML files created in Pluto.jl.

### styles.css

CSS styles for index.html.

### notebooks

All Pluto.jl notebooks, rendered to static HTML.
