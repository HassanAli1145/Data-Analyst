
# Real Estate Management-Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/767af1fe-8c81-49cc-ba81-8211f185856b/ReportSection

## Problem Statement

This dashboard helps the Real Estate Property Advisor and customers to understand the property details based on different factors.  Through different factors,they get to know their perfect place,
It also lets them know the price and condition details, thus since by using this dashboard they have identified this problem.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors.
- Step 5 : Data was refined in form of dimension and fact tables by making duplicates and using Merge Queries. 
- Step 6 : After this we will close and apply the Power Query editor.
- Step 7 : Multiple Measures were added i.e. for Total Property, Waterfront , Renovation,Condition and there percentages.It define us whether the factor is Yes or Not and tells us the total property based on factor. 
DAX Expression for Total Properties:
	
    Total Properties = COUNTROWS(FactTable)
DAX Expression for Waterfront :
	
    Waterfront Y = CALCULATE([Total Properties],FILTER(FactTable,FactTable[WaterFront ID]=1))
	Waterfront N = CALCULATE([Total Properties],Dim_WaterFront[WaterFront]="No")
There Percentages:
	
    %Waterfront Y = DIVIDE([Waterfront Y],[Total Properties],0)
	%Waterfront N = DIVIDE([Waterfront N],[Total Properties],0)
DAX Expression for Renovation:
	
    Renovated Y = CALCULATE([Total Properties],FILTER(FactTable,FactTable[Renovate ID]=1))
	Renovated N = CALCULATE([Total Properties],FILTER(FactTable,FactTable[Renovate ID]=0))
There Percentages:
	
    %Renovate Y = DIVIDE([Renovated Y],[Total Properties],0)
	%Renovate N = DIVIDE([Renovated N],[Total Properties],0)
DAX Expression for Waterfront :
	
    Very Good = CALCULATE([Total Properties],Dim_ConditionStatus[Condition]="Very Good")
	Good = CALCULATE([Total Properties],Dim_ConditionStatus[Condition]="Good")
	Bad = CALCULATE([Total Properties],Dim_ConditionStatus[Condition]="Bad")
There Percentages:

	%Very Good = DIVIDE([Very Good],[Total Properties],0)
	%Good = DIVIDE([Good],[Total Properties],0)
	%Bad = DIVIDE([Bad],[Total Properties],0)
- Step 8 : Firstly we have made the background design on figma and exported it and fit it at the background of the canvas. 
![Untitled (3)](https://github.com/user-attachments/assets/49d396f3-a7d7-41cf-b841-d6f45871f58c)
- Step 9 : It includes One Rctangle rounded corners on left side and other 6 on right side.
- Step 10 : In the report view, under the insert tab, Five text boxes were added to the canvas,and named each visuals title.
- Step 11 : Then we build the first visual i.e. stacked bar chart for Bedrooms vs Total Properties.It will show us the total property with respect to bedrooms numbers.
- Step 12 : Second visual i.e. stacked bar chart for Floors vs Total Properties.It will show us the total property with respect to bedrooms numbers.
- Step 13 : Third Visual i.e. line chart that shows the year built and total property. 
- Step 14 : On left side we have charts related to location.  
- Step 15 : Locations Slicer has been added and two stacked bar charts were added i.e. Location vs Price and Location vs SQFT. 
- Step 16 : Slicers were adjusted to only give effect on these two charts by editing the interactions.
- Step 17 : We will add 7 cards in which two are for water front,two for renovation and three for condition.
- Step 18 : Also 7 other cards for each one for percentage results.
- Step 19 : We will add the second page that was named as Location.
- Step 20 : On second page we will add Map to locate the location geographically.
- Step 21 : Then we will add three tables on left side that is Condition vs Location,Bedrooms and Floors.
- Step 22 : Now to navigate from one page to another we use Page Navigator from inserts -> Buttons -> Navigator -> Page Navigator.
- Step 23 : Now we will add the filters by adding slicers and group them at one button tat will show when we press it and hides on other button.
- Step 24 : Another button was added to clear the filters.
- Step 25 : Publish the report by clicking on the button.
## Dashboard Snaps
### OverView
![1 (1)](https://github.com/user-attachments/assets/d8177c65-63c4-45f4-8ef7-65e1431e8c77)
### Location
![2](https://github.com/user-attachments/assets/985d2363-4973-40d7-bed7-931382a29956)





