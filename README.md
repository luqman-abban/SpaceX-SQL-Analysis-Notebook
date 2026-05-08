# SpaceX SQL Analysis Notebook

## Overview

This project contains SQL-based analysis of the SpaceX launch dataset using Python, SQLite, and Jupyter Notebook. The notebook demonstrates how SQL queries can be used to explore launch mission data, payload information, landing outcomes, and booster performance.

The analysis is part of a peer assignment focused on applying SQL concepts to a real-world dataset.

---

## Objectives

Using this notebook, the following tasks were completed:

* Load the SpaceX dataset into a SQLite database
* Execute SQL queries using `ipython-sql`
* Analyze launch sites, payloads, booster versions, and landing outcomes
* Practice SQL operations such as:

  * `SELECT`
  * `DISTINCT`
  * `WHERE`
  * `GROUP BY`
  * `ORDER BY`
  * Aggregate functions (`SUM`, `AVG`, `COUNT`, `MAX`, `MIN`)
  * Subqueries
  * String filtering with `LIKE`

---

## Technologies Used

* Python
* Jupyter Notebook
* SQLite
* Pandas
* SQLAlchemy
* ipython-sql

---

## Dataset

The dataset used in this project contains records of SpaceX launches, including:

* Launch site
* Booster version
* Payload mass
* Customer
* Mission outcome
* Landing outcome
* Launch date

Dataset source:

IBM Skills Network / SpaceX Dataset

---

## Setup Instructions

### 1. Install Required Libraries

```python
!pip install sqlalchemy==1.3.9
!pip install ipython-sql prettytable
!pip install pandas
```

### 2. Load SQL Extension

```python
%load_ext sql
```

### 3. Connect to SQLite Database

```python
import sqlite3
con = sqlite3.connect("my_data1.db")
```

### 4. Load Dataset

```python
import pandas as pd
df = pd.read_csv("Spacex.csv")
```

### 5. Store Dataset into Database

```python
df.to_sql("SPACEXTBL", con, if_exists='replace', index=False)
```

---

## SQL Tasks Completed

### Task 1

Display unique launch sites.

### Task 2

Display records where launch sites begin with "CCA".

### Task 3

Calculate total payload mass carried by NASA (CRS).

### Task 4

Calculate average payload mass carried by booster version F9 v1.1.

### Task 5

Find the first successful ground pad landing date.

### Task 6

List boosters with successful drone ship landings carrying payloads between 4000 and 6000 kg.

### Task 7

Count successful and failed mission outcomes.

### Task 8

Find booster versions carrying the maximum payload mass.

### Task 9

Display failure drone ship landings during 2015 with month information.

### Task 10

Rank landing outcomes between 2010-06-04 and 2017-03-20.

---

## Example Query

```sql
SELECT Landing_Outcome, COUNT(Landing_Outcome) AS Count
FROM SPACEXTABLE
WHERE Date BETWEEN '2010-06-04' AND '2017-03-20'
GROUP BY Landing_Outcome
ORDER BY Count DESC;
```

---

## Key Learnings

Through this project, the following concepts were practiced:

* SQL database creation and management
* Data loading using Pandas
* Writing analytical SQL queries
* Using aggregate functions
* Working with subqueries
* Filtering and grouping data
* Integrating SQL with Python notebooks

---

## Project Structure

```text
├── SpaceX_SQL_Notebook.ipynb
├── README.md
└── Spacex.csv
```

---

## Author

Luqman Abban

---

## Acknowledgements

* IBM Skills Network
* SpaceX Dataset
* Coursera Data Science Program
