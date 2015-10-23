# Responsive-Grid-with-json-data
Create grid using 6-7 steps using mps javascript library,which supports responsive css and common functionality like Export,sorting and filter on client side.

Grid Layout
![mpsgrid](https://cloud.githubusercontent.com/assets/9654044/10635052/854976e8-7813-11e5-95c0-5e699b885433.png)

In Responsive Screen

![responsivempsgrid](https://cloud.githubusercontent.com/assets/9654044/10635047/7bac81a2-7813-11e5-83b7-b8e616a26243.png)

# Supported browsers are IE10+,Firefox,Chrome and Safari.

# this grid also handle large data sets.
--for test purpose i have tried with 80k records,its working perfectly.
# To Create Grid all you need to follow the below steps
-Add below js and css reference in your page
```html
<script src="mpsScript.min.js" type="text/javascript"></script>
<link rel="stylesheet" href="responsive.css"/>
```
-Add div element for the grid with id
```html
<div  id="data"></div>
```
-Add Pagination div with id
```html
 <div id="pageNavPosition"></div>
 ```
 add below code to create grid in script tag
 ```html
        Grid.Id = "data";
        //pass id and Table css className
        var grd = Grid.CreateGrid("data", "responstable");
        var colNames = "_id,index,guid,isActive,balance,age,eyeColor,name,gender,company,email,phone,address";
           
        //Provide Column Names
        Grid.SetColumnHeader(grd, colNames);

        //Provide Json Object data source
        Grid.setData(JsonData);
       //Set paging information,pass grid id and records per page
        Grid.SetPaging('data', 5);
        //to set hyperlink on grid's data,
        //Grid.HyperLink('columnName on which hyperlink should displayed', 'url with id like CustomerDash.aspx?id=', 'parameter of id col name cust_id', '')
        Grid.SetHyperLink('name', 'CustomerDash.aspx?id=', '_id');
        Grid.Bind();
        Grid.isDomReady();
        //set Export file name
        Grid.SetExportFileName('CustomerReport');
  ```
        
