# SQL_population_project 2
This is World Wide DATABASE from 2000 to 2010 . And i applied some common SQL queries on it.


### Prerequsites
Basic SQL commnads or Operators only. :wink:


* First we will download our DATABASE from here [sql-population-queries-part-2](https://codecademy-content.s3.amazonaws.com/PRO/independent-practice-projects/sql-population-queries/sql-population-queries-part-ii-starting.zip)

I think all set now we will do fun :wink:

* you already see how to set it up in first part now move on 

----
### Let's Go
* This time our schema are

---
**country**

| Columns | Type | notes |
| ----------- | ----------- |----------- |
| id | integer | primary key |
| name | Text | 
| continent | Text |

---

---
**population_years**

| Columns | Type | notes |
| ----------- | ----------- |----------- |
| id | Integer| Primary key |
| population | Number | (in milions) |
| year | Number |
| country_id | Integer | Foregin Key |

---
