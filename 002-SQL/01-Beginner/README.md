# Instruction 

### Duration

30 minutes

### Competencies 
- Basic SQL coding skills 
- Ability to synthesize requirements and turn it into code 
- Analytical SQL concepts 
- Common table expressions 
- Window functions
- SQL teaching skills

### Environment
- SQL Editor: https://sqliteonline.com/
- SQLite syntax 

### Resources for candidate 

Starting code is provided as a `.zip` file. 

You can zip the files up by running [package_zip.sh](./package_zip.sh):

```
cd instruction
. ./package_zip.sh
```

### Background knowledge 

Basic SQL is the foundations of being able to interact with relational databases and fundamental to roles in data & analytics.

You may use Google to search for specific syntax. 

## Challenge parts 


#### Part 1: Restoring the database 

The candidate restores the database by copying the SQL code in chinook_db.sql and running it in the SQL Editor (https://sqliteonline.com/). 


#### Part 2: Writing the analytical SQL query 

Obtain a list of customers that have purchased 2 or more tracks from the 'Alternative & Punk' genre for the month of November 2013, 
in descending order of track counts. 

#### Levelling
- Basic: Solves the question without using Common Table Expressions (CTEs). Jumps straight into the question without clarifying requirements or talking out loud. 
- Intermediate: Makes use of CTEs to solve the question and communicates as they go. 
- Advance: Considers SQL performance and places the CTEs in an order that will optimize performance. i.e. filtering comes first. 

#### Part 3: Detecting the problem 

You notice that data is skewed for Customer 42, 'Wyatt Girard'. What do you think is causing it? 

#### Levelling
- Basic: Proposes that duplicates may cause the issue, but cannot pinpoint which table the duplicates originate from. 
- Intermediate: Goes table by table and executes a query to determine if duplicates exist in the table. 
- Advance: Suspects that the root cause might be the `InvoiceLine` table as the duplicated data appears to be trackcount. Narrows down first to `InvoiceLine`.

#### Part 4: Fixing duplicates 

Fix the above query to address the issue detected in Step 3. 
