# San_Francisco_Crime-Python-PowerBi-
Have you ever thought about which day is the best to visit San Francisco or which places you should avoid? Well, San Francisco Police Department published a database of crime reports for the last 5 years, containing more than 700.000 rows and 27 columns.
<br>In this project, I will use Python to explore, clean, and prepare the dataset for visualization in Power Bi.


## Main questions:
**1) Which day of the week is the safest?** <br>

**2) Which place is better to avoid?**

**NOTE:** The code I published is the clean version of the original one. In the original code, I double-checked the data frame after each step, made some extra steps, etc.



### Get the data ready for visualization <br>
![step1](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/405b46d4-d704-4226-a446-aba6efe52cc5)<br>
Here we can see that some columns contain null values - missing values. And because I want to plot the data on a map later, I need to make sure that there aren´t any missing values for Lattitude and Longitude column 
![step2](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/f0ea5b2d-8b1b-4af1-9c0a-7fc025409dfc)<br>
To remove null values I used dropna() function for the Latitude column 
![step3](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/da80dc5e-de5b-441a-b86a-4947e7ee2185)<br>
After removing null values, the dataset size decreased by approximately 40.000 rows
![step4](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/f162bc66-a6e2-49e2-bf00-6871b3d05886)<br>
The dataset contains too many columns which are not important to this project, so I selected only the columns I will use
![step5](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/80118f8b-39f6-4706-b49d-891bb25c913a)<br>
And here comes the tricky part! Each crime has a date and time but from the logic, the crime which happened on Sunday at 3 am still belongs to Saturday night, I had to transform the Incident Datetime column to datetime object, create a new column with shifted time by 6 hours and a new day in the week column from the shifted time
![step6](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/77736840-2d03-42c3-a572-ce9de75107d1)
Finally, I saved the new data frame as a csv file for further analysis in Power Bi
![step7](https://github.com/Bzeorge/San_Francisco_Crime-Python-PowerBi-/assets/74241688/0c02f92c-91e1-4687-b80c-be57e2c74617)

### Visualize the data





