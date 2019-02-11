# ResponsiveGridSystem
The responsive grid system made using the CSS floats and CSS media query.

The process is composed of several steps:

* Step 1: Setting the `box-sizing` to `border-box`
* Step 2: Creating the grid container
* Step 3: Calculating the column width and the gutter (gap) position and size
* Step 4: Creating the layouts
* Step 5: Making the layouts responsive 

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
## Step 2: Creating the grid container
 The grid container determines the maximum width of the grid. In this example, it has a class name `.container`. 

 ```
 .container {
	width:60%;
	height:100%;
	margin: 0 auto; 
 }
 ```
Such class makes your content centered with `margin: 0 auto`, and takes 60% of the whole window. The width is set in % for responsive purposes. 

## Step 3: Calculating the column width and the gutter (gap) position and size 
The `.container` is divided into two big columns: one is for the main content - `.container_main`, and the other is for the sidebar -`.container_sidebar`.

```
<div class="container">
			
	<div class="container_main"></div>
	
	<div class="container_sidebar"></div>

</div>
```
```
.container_main{
	float: left;
	height: 100%;
	width: 70%;
	background-color: #E8FFD2;
	border: 1px solid gray;
	
}

.container_sidebar{
	height: 100%;
	width: 30%;
	float: right;
	background-color: #E8FFD2;
	border: 1px solid gray;
}
```
The same principle can be applied when adding items within the `.container_main` and `.container_sidebar`.

```
<div class="container">
			
	<div class="container_main">
		<div class="row">
			<div class="grid_item item">Item 1</div>
			<div class="grid_item item">Item 2</div>
			<div class="grid_item item">Item 3</div>
			<div class="grid_item item">Item 4</div>
			<div class="grid_item item">Item 5</div>
			<div class="grid_item item">Item 6</div>
			<div class="grid_item item">Item 7</div>
			<div class="grid_item item">Item 8</div>
		</div>
	</div>
	
	<div class="container_sidebar">
		<div class="sidebar_row">
			<div class="sidebar_item item">Sidebar Item 1</div>
			<div class="sidebar_item item">Sidebar Item 2</div>
			<div class="sidebar_item item">Sidebar Item 3</div>
			<div class="sidebar_item item">Sidebar Item 4</div>
		</div>
	</div>

</div>
```
The gutter position for the `.item` is added as margin, placed on both sides. For more information and possibilities, look at https://zellwk.com/blog/responsive-grid-system/. 

```
.item{
	margin:0.5rem;
	padding: 0.5rem;
}
```
To have three columns in one row, the width is calculated as
 `width: calc((100% - 6 * 0.5rem) / 3);`

 In this case, from 100% of the `.container_main` width, 6 margins size of 0.5rem are subtracted, and the width is divided by 3, to have a full width of the columns `.grid_item`.  

```

.grid_item{
	height: 300px;
	width: calc((100% - 6 * 0.5rem) / 3);
	background-color:#70FFD3;
	border: 1px solid gray;
	float:left;
	
}
```
Regarding `.sidebar_item`, the width is calculated as `width: calc(100% - 2*0.5rem);`. As the items in sidebar are arranged in only one column, there are 2 margins of 0.5rem for subtracting. 
```
.sidebar_item{
	width: calc(100% - 2*0.5rem);
	height: 100px;
	float:left;
	background-color:#70FFD3;
	border: 1px solid gray;
}
```