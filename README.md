![dec-logo](./admin/dec-logo.png)

# :mortar_board: Data Engineer Camp 

![python](https://img.shields.io/badge/python-lang-red)
![sql](https://img.shields.io/badge/sql-lang-red)
![bash](https://img.shields.io/badge/bash-lang-red)
![airbyte](https://img.shields.io/badge/snowflake-tool-blue)
![snowflake](https://img.shields.io/badge/snowflake-tool-blue)
![databricks](https://img.shields.io/badge/databricks-tool-blue)
![spark](https://img.shields.io/badge/spark-tool-blue)
![dbt](https://img.shields.io/badge/dbt-tool-blue)
![airflow](https://img.shields.io/badge/spark-tool-blue)
![preset](https://img.shields.io/badge/preset-tool-blue)
![kafka](https://img.shields.io/badge/kafka-tool-blue)
![druid](https://img.shields.io/badge/druid-tool-blue)
![git](https://img.shields.io/badge/git-tool-blue)
![github-actions](https://img.shields.io/badge/ghactions-tool-blue)
![docker](https://img.shields.io/badge/docker-tool-blue)
![aws](https://img.shields.io/badge/aws-tool-blue)

## :wave: Welcome 

Welcome to the Data Engineer Camp bootcamp repo. The bootcamp is designed to teach aspiring data engineers the skills to become a proficient data engineer with the modern data stack. 

## :date: Bootcamp timetable 

| Day/Time | Activity | 
| - | - | 
| Monday, 10:00am - 1:00pm (UTC) | Live class | 
| Tuesday, 10:00am - 1:00pm (UTC) | Live class | 
| Thursday, 10:00am - 1:00pm (UTC) | Live class | 
| Saturday, 12:00am - 2:00am (UTC) | (Optional) Live support hours | 

:arrow_down: Click on the Google Calendar icon to view a lesson by lesson breakdown. 

[![Bootcamp calendar](./admin/bootcamp-calendar.png)](https://calendar.google.com/calendar/embed?src=c_64401dd61c98cc94504a33286e914e8a0e7c78edfab7301f802186777e7946b5%40group.calendar.google.com&ctz=Australia/Perth)

:exclamation: You can change the timezone of the calendar to your local timezone by changing the country timezone parameter in the URL: 

Example URL: 

```
https://calendar.google.com/calendar/embed?src=c_64401dd61c98cc94504a33286e914e8a0e7c78edfab7301f802186777e7946b5%40group.calendar.google.com&ctz=Australia/Perth
```

You can modify the country timezone parameter: 

```
ctz=<your_local_timezone> 
```

Where: 
- `your_local_timezone`: Your local timezone in the IANA format e.g. `Australia/Sydney`, `America/Los_Angeles`. See a list of IANA timezone format here: https://nodatime.org/TimeZones

## :open_file_folder: Repository structure 

Please read this section to understand how to navigate the repository. 

The contents of the repository is broken down as follows: 

```
root 
|__ <topic_number>-<topic_title>
    |__ README.md
    |__ <lesson_num>
        |__ <activity_num>-<activity_type>-<activity_title>
            |__ instruction/README.md
            |__ solved/*
            |__ unsolved/*
```

- `topic_number`: refers to the topic number e.g. 01, 02, 03. 
- `topic_title`: refers to the week's topic e.g. Python ETL, SQL ETL. 
- `lesson_num`: refers to the lesson number i.e. 1 or 2 or 3. 
- `activity_num` : refers to the activity number e.g. 01, 02, 03. 
- `activity_type`: refers to the activity type i.e. `ins` instructor, `stu` student, `evr` everyone. 
- `activity_title`: refers to the activity title e.g. Extracting data, transforming data. 

Example: 
```
root 
|__ 01-python-etl
    |__ 1
        |__ 03-ins-extracting-data
            |__ instruction/README.md
            |__ solved/*
            |__ unsolved/*
        |__ 04-stu-extracting-data
            |__ instruction/README.md
            |__ solved/*
            |__ unsolved/*
```


Each activity contains the following folders: 
- `instruction`: contains a `README.md` file along with other files related to the instruction for the activity. 
- `solved`: contains the solved solutions for the activity. [`stu`] solved solutions will be uploaded at the end of each class. 
- `unsolved`: contains the unsolved starting code for the activity. This folder may be empty at times if the code is to be created from scratch. 

