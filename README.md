# Measuring Business Value and Productivity Beta Site

## Setup

Install [Julia](https://julialang.org/), [Pluto.jl](https://plutojl.org/), and [VSCode](https://code.visualstudio.com/) (or another code editor with support for HTML/CSS/JS and Julia).

## Adding Pages

If updating an existing page, only step 1 is required. If adding a new page to the site, follow all steps below.

### 1. Export Pluto.jl Notebook to HTML

> Make sure that all code (including Markdown) that you do not wish to display is hidden before exporting by clicking the _Show/hide code_ (👁) button located near the top left of each code cell.

Click the export button located at the top right of the Pluto.jl notebook (see below). Select **Static HTML**, then **Download HTML File**. Note that the downloaded HTML file will have the same name as the corresponding .jl file.

![Export](images/exportbutton.jpg)

### 2. Update index.html

The following example assumes that the file you wish to add is named _example.html_ and is has title _This is an example title_.

#### a. Update HTML

Find the toc div, which can be done by using `Ctrl (or Cmd) + F` and entering _Add new HTML page buttons here_. Add a button for the new HTML file in the location that you wish it to appear in the table of contents. For example, if you wish to list the file 3rd in the table of contents:

```
<button id="example" class="toc-entry" onclick="changeTab(2)">This is an example title</button>
```

> **Note:** The number used in the call to _changeTab_ should be one less than the file's location in the table of contents. Additionally, make sure you update the calls to _changeTab_ for all buttons appearing after the new button accordingly.

#### b. Update JavaScript

Find the tab content objects and _tabContents_ array, which can be done by using `Ctrl (or Cmd) + F` and entering _Add new HTML page objects here_. Create a new JavaScript object as follows:

```
const example = {name: "example", title: "This is an example title"}
```

Then, add this object to the _tabContents_ array **in the same location as it appears in the table of contents.**

## Files

### index.html

The main HTML page. Used to display and navigate between the HTML files created in Pluto.jl.

### styles.css

CSS styles for index.html.

### Other HTML files

TODO
