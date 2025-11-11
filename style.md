# Style Guide

The following guidelines are used for formatting and coding style in each Pluto.jl file.

## Formatting

To ensure consistent sizing, include the following in a hidden cell at the bottom of each Pluto notebook added to the website. 

```
using PlutoUI
begin
	HTML("""
	<style>
	  main {
	    max-width: 58vw !important;
	    margin-right: 25vw !important;
	  }
	</style>
	""")
end
```

For longer notebooks that include mutliple subsections, include the following in a hidden cell at the bottom of the notebook.

```
begin
	using PlutoUI
	TableOfContents()
end
```

## Coding Style

See the [Julia Style Guide](https://docs.julialang.org/en/v1/manual/style-guide/) for the baseline guidelines.

Pluto.jl requires that all cells of Julia code longer than one line must be wrapped in a function, module, macro, or begin-end block. Use functions, macros, and modules as they would be used in a regular .jl file. Group all other lines of code logically into begin-end blocks, interspersting Markdown cells for documentation as needed.
