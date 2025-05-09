Name: Fuad Choudhury\
Course: CIS4400, Semester: Spring 2025\
Professor: Jefferson Bien-Aime\
Topic: Homework

# Movie Rating Analysis based on IMDB
This project provides a complete solution for analyzing IMDb movie ratings with cloud technology. It includes steps for extracting, loading, transforming, modeling, and visualizing data to gain insights into movie ratings and viewer behavior over time.

Moreover, this project began by collecting and cleaning IMDb movie rating data to analyze and compare movie performance. I modeled the data using a star schema in Snowflake, then visualized it in Tableau. The dashboard helps users easily discover top-rated movies by year or genre. It's effective because it turns raw data into clear, interactive insights for movie lovers and analysts alike.

# Business Requirements:
Goal: Based on IMDb ratings, analyze and compare three to four movies to determine which one has the highest rating.

•	Enable users to quickly discover top-rated movies based on IMDb data.

•	Integrate release year information to give additional context to movie ratings.

•	Support informed decision-making for movie selection through data-driven insights.

# Functional Requirements:
A simple program that allows users to compare movie ratings.

•	The interface should be user-friendly and provide relevant details.

•	Display the release year along with the rating score for better comparison.

•	Users can filter movies based on year to find top-rated films.

•	Provide the option to compare multiple movies.

•	Include graphical analysis for visual comparison.

# Datasets Used:
title.basics.csv: Contains metadata for movies (title, runtime, genre, etc.)

title.ratings.csv: Contains IMDb average ratings and vote counts

# Information Architecture:
The information architecture for the Movie Rating Analysis Based on IMDb project illustrates the end-to-end workflow of processing IMDb data to prepare it for analysis and reporting. The project utilizes two main datasets: Title Basic, which includes metadata about movies, and Title Rating, which contains rating information. These datasets are collected from IMDb in CSV format and temporarily stored for initial processing. The data then undergoes a cleaning stage to eliminate missing values and correct formatting issues, followed by a reformatting step where data types are standardized and column names are updated for consistency. In the transformation phase, the cleaned datasets are joined and new attributes are derived, such as computed metrics or normalized formats. Once transformed, the data is consolidated into structured tables and loaded into a centralized data warehouse hosted on Microsoft Azure. This warehouse serves as the foundation for efficient querying and downstream analysis.

![image](https://github.com/user-attachments/assets/73d4b897-9e00-43dc-bd54-67dec77796c9)


# Data Architecture:
The data architecture represents the overall data pipeline at a high level. It begins with the ingestion of raw IMDb data, which is first stored temporarily before undergoing an integration process. This process includes all steps such as cleaning, transforming, and merging the datasets, as detailed in the information architecture. The integrated data is then loaded into a data warehouse where it is organized and optimized for performance. Finally, the data is made available to visualization tools for building reports, dashboards, and conducting deeper analytical exploration.

![image](https://github.com/user-attachments/assets/55c3682e-d8b4-4491-b0fa-4228983d1659)


# Dimensional Modeling:

•	The data warehouse is composed of a fact table that includes ratings, votes, and the year, along with dimension tables that classify movies based on their release year. 

•	Also, a surrogate key is employed for both the fact and dimension tables.
![image](https://github.com/user-attachments/assets/36afbebf-8cc2-4418-b576-db00cc6fea05)


Star schema design with surrogate keys:

Fact and dimension tables prepared for querying.

Data warehouse schema: analytics
![star_schema](https://github.com/user-attachments/assets/dddd179c-6eec-41fe-8e10-24c5ea9fa2e0)



# Technical Architecture:
The IMDb Movie Rating Analysis project processes and analyzes movie ratings through a series of steps. First, raw IMDb datasets (`title.basics.csv` and `title.ratings.csv`) are stored in Azure Blob Storage. The data is then loaded into Snowflake, where it is cleaned, transformed, and combined into a consolidated table. Python is used for running queries and generating visualizations for analysis. The architecture ensures efficient data storage, transformation, and scalable analysis, with the option for a front-end interface for user interactions.
![1](https://github.com/user-attachments/assets/0761c732-4e90-42a5-a25b-4fd9bd5e0643)

# Tools Used:
Azure Blob Storage; for Cloud storage for raw and cleaned datasets

Snowflake; for Cloud data warehouse for ELT & data modeling

SQL; for Data transformation and schema creation

Python; for Data ingestion, validation, and API generation

Tableau; for Data visualization and dashboard creation

Git & GitHub; for Version control and collaboration

# Data Pipeline Steps:
•	Data Sourcing:

IMDb datasets sourced from IMDb Datasets. Data dictionary created to describe fields, types, and constraints

•	Data Storage: Cleaned data uploaded to Azure Blob Storage. Data loaded into Snowflake tables (titles, ratings)

•	Data Transformation (ELT): Created combined table movie_combined in Snowflake.

Structured dimensional model with:

fact_movie_ratings

dim_movie

dim_date

Removed duplicates, handled nulls, unified formats, and split dates

•	Data Modeling:

Star schema design with surrogate keys. Fact and dimension tables prepared for querying

Data warehouse schema: analytics
![star_schema](https://github.com/user-attachments/assets/dfa2c7e3-82ef-4f1a-9e08-b2856ac6f894)

•	Serving Data
Dashboards built using Tableau
![data_flow](https://github.com/user-attachments/assets/7a0f7367-c2f5-41f5-b17c-c77cd0ab4b93)

# Data Visualization Screenshot:
![image](https://github.com/user-attachments/assets/5a85bc86-dfbd-47a1-8a28-4a74b96f30c2)
It’s done by Tableau Public to the exported CSV datasets and created interactive visualizations.

Visualizations:

1.	Top 10 Movies by Average Rating (Bar Chart with filter > 100 votes)

2.	Movie Ratings and Votes Over Year (Line Chart with release year)

3.	Movie Ratings and Votes by Genre (Column Chart)

Filter: Global filter added for year range.

# Deliverables:
•	Links to data sources (https://datasets.imdbws.com/)\
•	Azure Storage Link:

•	Blob-SAS-Token:
sp=r&st=2025-05-03T20:09:13Z&se=2025-05-31T04:09:13Z&spr=https&sv=2024-11-04&sr=c&sig=yS7zZiabUpvHN5lEa0zoCvtYR4PVXdtqU21tv6vVvQE%3D

•	Blob-SAS-URL: https://cis4400datastorage2025.blob.core.windows.net/cis4400homework?sp=r&st=2025-05-03T20:09:13Z&se=2025-05-31T04:09:13Z&spr=https&sv=2024-11-04&sr=c&sig=yS7zZiabUpvHN5lEa0zoCvtYR4PVXdtqU21tv6vVvQE%3D


•	Data origin: IMDb Non-Commercial Datasets; Customers can access subsets of IMDb data for personal and non-commercial purposes.(https://developer.imdb.com/non-commercial-datasets/)

•	Data dictionary: (Using MS Excel, MS Word)

•	This Git repository Link: (https://github.com/fuadchoudhury/CIS4400_Homework)

•	Data Model/Diagrams: (Using Draw.io)

•	Data Warehouse: Created in AWS Redshift; since snowflake used for create, populate, structure tables and verify dimensional model and connect to Tableau for visualization.

•	Accessible IMDb Data Warehouse:(https://developer.imdb.com/non-commercial-datasets/)
