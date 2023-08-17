# San_Francisco_Crime-Python-PowerBi-
Have you ever thought about which day is the best to visit San Francisco or which places you should avoid? Well, San Francisco Police Department published a database of crime reports for the last 5 years, containing more than 700.000 rows and 27 columns.
<br>In this project, I will use Python to explore, clean, and prepare the dataset for visualization in Power Bi.


## Main questions:
**1) Which day of the week is the safest?** <br>

**2) Which place is better to avoid?**

**NOTE:** The code I published is the clean version of the original one. In the original code, I double-checked the data frame after each step, made some extra steps, etc.



### Get the data ready for visualization <br>
![step1](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/405b46d4-d704-4226-a446-aba6efe52cc5)<br>
<br>
Here we can see that some columns contain null values - missing values. And because I want to plot the data on a map later, I need to make sure that there aren´t any missing values for Lattitude and Longitude column 
![step2](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/f0ea5b2d-8b1b-4af1-9c0a-7fc025409dfc)<br>
<br>
To remove null values I used dropna() function for the Latitude column 
![step3](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/da80dc5e-de5b-441a-b86a-4947e7ee2185)<br>
<br>
After removing null values, the dataset size decreased by approximately 40.000 rows
![step4](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/f162bc66-a6e2-49e2-bf00-6871b3d05886)<br>
<br>
The dataset contains too many columns which are not important to this project, so I selected only the columns I will use
![step5](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/80118f8b-39f6-4706-b49d-891bb25c913a)<br>
<br>
And here comes the tricky part! Each crime has a date and time but from the logic, the crime which happened on Sunday at 3 am still belongs to Saturday night, I had to transform the Incident Datetime column to datetime object, create a new column with shifted time by 6 hours and a new day in the week column from the shifted time
![step6](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/77736840-2d03-42c3-a572-ce9de75107d1)<br>
<br>
Finally, I saved the new data frame as a csv file for further analysis in Power Bi
![step7](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/0c02f92c-91e1-4687-b80c-be57e2c74617)<br>

### Data Visualization
After importing the data set I noticed that Latitude and Longitude were formatted as a text
![stepy1](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/830fec5f-1688-4c89-b5fe-becda35df40d)<br>
<br>
For proper function, I had to change the data type of the columns
![stepy2](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/32394d0f-d090-4ab7-be6a-6c2785c7911e)<br>
<br>
A few steps later, I created an interactive dashboard with 3 charts and one slicer(filter) on the first page
![stepy3](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/516e3e04-07a8-44f1-9165-08fb4e9cfd60)<br>
<br>
And heat map with a slicer and two charts on the second page
![stepy4](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/30f87600-b4bf-4b6d-afbe-bd1be22f55f0)<br>
<br>
### Conclusion
The data visualization helped me to clearly identify the day of the week and month with the highest crime rate as well as the places with the highest concentration of those crimes. During the analysis, I found one interesting thing - the Motor Vehicle Theft is continuously rising each year!
![stepy5](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/9eaa5c84-3451-4f2d-8df1-3e4b6e516630)<br>
<br>
**Thank you for your attention and don´t go to San Francisco on a Friday or in July** *(just my recommendation) 
* Data source: https://data.sfgov.org/Public-Safety/Police-Department-Incident-Reports-2018-to-Present/wg3w-h783



