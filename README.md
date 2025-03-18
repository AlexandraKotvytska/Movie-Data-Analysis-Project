# Movie Data Analysis Project

## Table of Content
 - [Project Overview](#project-overview)
 - [Data Sources](#data-sources)
 - [Tools](#tools)
 - [Data Cleaning and Preparation](#data-cleaning-and-preparation)
 - [Questions for Data Analysis](#questions-for-data-analysis)
 - [Dashboard](#dashboard)
 - [Results and Findings](#results-and-findings)
 - [Chalanges in Analysis](#chalanges-in-analysis)
   
### Project Overview
This data analysis project aims to provide insights into the performance and trends of movies from 2012 to 2016 to the team of creative directors of Apple TV. By analyzing various aspects of the movie data, we seek to identify patterns, make data-driven recommendations, and gain a deeper understanding of the industry's dynamics.

### Data Sources
 Movie Data : The primary dataset used for this analysis is the "Movie Data Homework.xmls" file, containing detailed information about each movie's performance (box office and budget), actors, directors etc. [Find the original Data Source Here.](https://github.com/AlexandraKotvytska/Movie-Data-Analysis-Project/upload/main#:~:text=Movies%20Dashboard.xlsx)

### Tools
  - Power Query - I used Power Query for Data Cleaning
  - Excel - I used them for Data Analysis
    - Pivot Table- for Creating dashboard and Visualizations

### Data Cleaning and Preparation
In the initial data preparation phase, I performed the following tasks:
Data loading and inspection.
Handling errors, missing values.
Data cleaning and formatting. The excel file after the data cleaning & preparation process can be downloaded here - [Movies Data Ready for Dashboard.](https://github.com/AlexandraKotvytska/Movie-Data-Analysis-Project/upload/main#:~:text=Movies%20Dashboard.xlsx)

### Questions for Data Analysis
 1. Which top 10 genres were the most successful (Box) these years?
 2. Which top 5 actors were the most successful?
 3. Top5 movies Box and Budget?
   
### Dashboard
![Screenshot 173950](https://github.com/user-attachments/assets/3b7163f3-1963-42a4-947a-7b97d4bc1d5a)

### Results and Findings
As an example: Best profitable movie  during 2012-2016 was: with Budget of... Box Office Revenue was 102,000,000 USD. The genre of this movie was horror.
![Screenshot 174019](https://github.com/user-attachments/assets/7bff97f3-d29f-40e8-a4b2-9af666c4dafd)
               
### Chalanges in Analysis
One of interesting features/ challenges I was working with was a specific code for Grouping in M language which enabled me to Combine genres together for further analysis. We had 2 column for genres, but we needed to combine them and have the same format, for example action/comedy, not comedy/action.

```
= Table.Group(#"Sorted Rows1", {"Movie Title"}, 
                                            {{"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},
                                            {"AllData", each _, 
                                                        type table [Movie Title=nullable text, Release Date=nullable date, Wikipedia URL=nullable text, Concat Genre=nullable text, Director=nullable text, Actor First=nullable text, Actor Second=nullable text, Actor Third=nullable text, Actor Fourth=nullable text, Actor Fifth=nullable text, #"Budget ($)"=nullable number, #"Box Office Revenue ($)"=nullable number]}
```
                                          
