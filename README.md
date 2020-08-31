# SQL_population_project
This is World Wide DATABASE from 2000 to 2010 . And i applied some common SQL queries on it.

### Prerequsites
Basic SQL commnads or Operators only. :wink:


* First we will download our DATABASE from here [sql-population-queries-starting](https://s3.amazonaws.com/codecademy-content/PRO/independent-practice-projects/sql-population-queries/sql-population-queries-starting.zip)

* Now download Sqlite3 from here [sqlite.org](https://www.sqlite.org/download.html)
`use a program that has command-line shell , sqldif , sqlite3 analyser`

* It will be in zip file extract it and set your path i.e environment variable in windows 
* Else you can use DB browser download from here [DB browser](https://sqlitebrowser.org)

I think all set now we will do fun :wink:

----
### Let's Go
* Now we will map to our downloaded directory and extract our database . you will find `db.sqlite` and `population_queires.sql` files.
```
**Type**
sqlite3 db.sqlite
````
* you can see your loaded databse schema with this command
```
*type*
.schema
```
* you will see on screen
```
CREATE TABLE population_years (
      country STRING NOT NULL,
      population NUMBER,
      year NUMBER
    );

```
* so your `database schemas` are **NOTE table name** is `population_years`
---
| Columns | Type | notes |
| ----------- | ----------- |----------- |
| country | string |
| population | number | (in milions) |
| year | number |
---

#### Now its time to work on commands

1.**_To retrive all data from table_**
```
SELECT * FROM population_years;
```
2.**_What is the largest population size for Gabon in this dataset?_**
```
SELECT * FROM population_years
WHERE country LIKE '%Gabon%'
ORDER BY population DESC
LIMIT 2;
```
output is

---
| Country | population | year |
| ----------- | ----------- |----------- |
| Gabon | 1.54526 | 2010 |
| Gabon | 1.51499 | 2009 |

---

3.**_What were the 10 lowest population countries in 2005?_**
```
SELECT * FROM population_years
WHERE year IS'2005'
ORDER BY population ASC
LIMIT 10;
```
output is

---
| Country | population | year |
| ----------- | ----------- |----------- |
|Niue	|0.00216	|2005|
|Falkland Islands (Islas Malvinas)|	0.00297|	2005|
|Montserrat	|0.00453	|2005|
|Saint Pierre and Miquelon|	0.0062|	2005|
|Saint Helena|	0.00748|	2005|
|Nauru|	0.01001|	2005|
|Cook Islands|	0.0136|	2005|
|Turks and Caicos Islands|	0.02057|	2005|
|Virgin Islands, British|	0.02268|	2005|
|Gibraltar|	0.02846|	2005|

---

4.**_What are all the distinct countries with a population of over 100 million in the year 2010?_**
```
SELECT DISTINCT COUNTRY FROM population_years
WHERE year is '2010' AND population >100
ORDER BY population DESC;
```

output is

---
|country|
| -----|
|China|
|India|
|United States|
|Indonesia|
|Brazil|
|Pakistan|
|Bangladesh|
|Nigeria|
|Russia|
|Japan|
|Mexico|

---
5.**_How many countries in this dataset have the word “Islands” in their name?_**
```
SELECT country FROM population_years
WHERE country LIKE '%_sland%';
```
6.**_What is the difference in population between 2000 and 2010 in Indonesia?_**
```
SELECT * from population_years
where country='Indonesia'and year='2000'
or country='Indonesia'and year='2010';
```

output is

---
| Country | population | year |
| ----------- | ----------- |----------- |
| Indonesia | 214.67661 | 2000 |
| Indonesia | 242.96834 | 2010 |

---
