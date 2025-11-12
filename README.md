# Measuring Business Value and Productivity Beta Site

## Setup

Install [Julia](https://julialang.org/), [Pluto.jl](https://plutojl.org/), and [VSCode](https://code.visualstudio.com/) (or another code editor with support for HTML/CSS/JS and Julia).

## Editing/Adding Pages

For a short guide to editing and creating Pluto notebooks, see [https://isaiahdal.github.io/](https://isaiahdal.github.io/). 

If updating an existing page, only step 1 is required. If adding a new page to the site, follow all steps below. Additionally, see [style.md](https://github.com/IsaiahDal/isaiahdal.github.io/blob/main/style.md) for some basic coding standards.

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
