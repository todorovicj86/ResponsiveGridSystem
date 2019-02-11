# ResponsiveGridSystem
The responsive grid system made using the CSS floats and CSS media query.

The process is composed of several steps:

* Step 1: Setting the `box-sizing` to `border-box`
* Step 2: Creating the grid conatiner
* Step 3: Calculating the column width
* Step 4: Creating the gutter (gap) position and size
* Step 5: Creating the layouts
* Step 6: Making the layouts responsive 

More detailed explanations are given at https://zellwk.com/blog/responsive-grid-system/. 

## Step 1: Setting the `box-sizing` to `border-box`
To create grid system, the box-sizing is set to border-box, for easier calculations of column's and gutter's sizes. 

```

html {
	-webkit-box-sizing:border-box;
	-moz-box-sizing:border-box;
	box-sizing:border-box;
}
*, *:after, *:before{
	-webkit-box-sizing:border-box;
	-moz-box-sizing:border-box;
	box-sizing:border-box;
}
```
