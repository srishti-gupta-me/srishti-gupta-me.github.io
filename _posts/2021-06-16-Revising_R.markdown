---
layout: post
title:  "Revising R"
date:   2021-06-16 05:38:32 +0530
categories: jekyll update
---

```
#This is a RScript file

#What and why R ?
# is a programming language that allows you to Store | Manipulate | Visualise data 

# 1. More powerful than Excel
# 2. Handle thousands of rows and many columns at a time 
# 3. Repetitive efforts can be reduced with programs 
# 4. Vast library of packages for data manipulation and visualisations
# 5. Cross-platform friendly : Can run on many operating systems.



# 1. Ctrl+L --> To clear the console
# 2. ls() to check the variables that are live in the environment
# 3. rm(variable_name) to remove variables

#Many packages are already part of RStudio, to install other packages , this command has to be run once only 

#install.packages("data.table"), already ran this command before sharing 

#After installing package in the RStudio, it needs to be brought to the environment , this means many packages can exist in the RStudio, 
#but needs to be extracted into the working environment 
library(data.table)

#For Documentation to any function and package
#1. ?function_name
#2. help(function_name/package_name)

#Tabular Data in R can be processed with 3 ways
#1.data.frame
#2.data.table (Advanced version of data.frame, today's focus)
#3.dplyr library

#Data Frames: 2 dimensional data structure
#Data frames store data as a sequence of columns and rows. Each column can be of a different data type.

#The file contains the dataset, this dataset has to be fed into a variable. function : read.csv("path_to_the_file",..,..), takes the dataset as a data.frame
dataframe <-read.csv("/cloud/project/TCPD_AE_Goa_2021-7-1.csv")
View(dataframe)

#Data Tables
#1. Data manipulation operations such as subset, group, update, join etc.
#2. reducing programming and compute time tremendously,

datatable <-fread("/cloud/project/TCPD_AE_Goa_2021-7-1.csv")
View(datatable)

#The way dataset is rendered, datatable and dataframe doesn't have difference
#However, in your console, you can see the left most column and find a ":", this is specific to datatable and is a 
#way to recognise

head(dataframe,2)
head(datatable,2)

#to view names of all the columns in the datatable
names(datatable)

#to understand the structure of datatable, variable types of each column
str(datatable)


#Use ctrl+l to clear the console

#Data Tables allow you to slice the dataset and update it

#DT[i, j, by]
#R: i j by
#i --> rows to select or operate on
#j --> select columns to operate on /update these columns ++ take these columns as a variable and operate on it 
#by ---> group by --> use the columns and rows and make unique groups

#Lets try to get the age of the candidate in the sort manner
#First lets find unique values 
unique(datatable$Age)

#Sort these unique values
sort(unique(datatable$Age))

#To see unique values in a column
unique(datatable$Election_Type)
unique(datatable$District_Name)

#Sort Names of Candidates Alphabetically, and update the datatable
order(datatable$Candidate, decreasing=FALSE, na.last=TRUE)
datatable <- datatable[order(datatable$Candidate, decreasing=TRUE, na.last=TRUE),]

datatable$Candidate <- sort(datatable$Candidate, decreasing = TRUE)
#na.last puts wherever a NA is encountered at the last of the dataset

#Now, we can see the age values, lets try selecting rows where age of candidate is 35 
result <- datatable[datatable$Age==35]


#Lets find what kind of variable is this 'result'
class(result)

#It is data.table, we can render to view
View(result)

#what is we wish to select some specific section of row, for example all rows between 20 to 40 serial number , 
#index starts from 1 as can be seen the datatable
datatable[20:40]

#Selecting single column and all rows 
result <- datatable[,~Month]
head(result)

#The error is because R is case sensitive

result <- datatable[,.(datatable$month)]
View(result)

#Multiple columns
result <- datatable[, c("month", "Age")]
head(result, 10)

#Data Tables allows to take columns as a variable, operate on it

#the below line of code, evaluate if sum of month and position is less than 3 for each row 
#and sends the results as TRUE/FALSE the period /. before the j part is used to deliver a list instead of a vector. 

#For now, you can just say that we will use this syntax to get vertical columns as output. 
#And see the difference between vectors and list, later.

result <- datatable[,.((month+Position)<3)]
View(result)

#Now if you want to add this new variable to the datatable, the variable will added in the last
datatable$new_var_MPos <- result


#Here the function is not subset/slicing based on columns it is decision making

# .N is a special character in R , containing the number of rows in the group.
#Useful when you dont know the columns names and want to work on the selected rows in i part

#Here we took all the rows, checked the unique values in the column District_Name and counted how many rows
#falls under which category
result =datatable[,.N,by=District_Name]
result

#More example, Now lets assume we want runner's up value only and discard winners' rows for now
# And we want to group by, how many candidates are runner up district wise

result =datatable[Position!=1,.N,by=District_Name]
result
#Here, we selected all the rows which has position not (!) equal to 1 , .N helped it taking all these rows and grouped by
#District_Name

#More example
result =datatable[Position=1,.N,by=.(District_Name,Candidate_Type)]
result

#Dependency for plotly sudo apt-get install libcurl4-openssl-dev
#install.packages("plotly")

library(plotly)

fig <- plot_ly(data = datatable, x = ~Party, y =~Position)
fig

fig <- plot_ly(data = datatable, x = ~District_Name, y =~Candidate_Type)
fig

fig <- plot_ly(data = datatable, x = ~District_Name, y =~Candidate_Type, type= histogram2d)
fig

fig <- plot_ly(data = datatable, x = ~Age, y =~Position)
fig <- fig %>% layout(title = 'Age versus Position', yaxis = list(zeroline = FALSE),xaxis = list(zeroline = FALSE))
fig

```

#Helpful Resources 
# 1. MOOCs: https://www.educative.io/courses/learn-r-from-scratch and many other
# 2. Documentation: https://rdrr.io/r/ , https://www.r-project.org/other-docs.html, help() , ?
# 3. Stack Overflow
# 4. Plotly: Visualisation library: https://plotly.com/r/

