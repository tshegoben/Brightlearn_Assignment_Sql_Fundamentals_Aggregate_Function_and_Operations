# Brightlearn_Assignment_Sql_Fundamentals_Aggregate_Function_and_Operations
Demontration of SQl Fundamentals
# SQL Fundamentals – Exercise 2: Aggregate Functions & Operators

## Overview

This repository documents my second SQL practice exercise as part of the BrightLearn Data Analytics course.

The exercise builds on the fundamentals of `SELECT` and filtering, introducing aggregate functions, grouping, and additional SQL operators. It focuses on retrieving, summarising, filtering, and organising data from multiple tables.

The exercise contains **15 SQL queries across five tables**, with an emphasis on understanding how SQL statements work and predicting the expected output.

## Learning Objectives

Through this exercise, I practise how to:

* Use aggregate functions such as `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()`.
* Group records using `GROUP BY`.
* Filter grouped results using `HAVING`.
* Apply operators such as `DISTINCT`, `BETWEEN`, `IN`, `NOT`, `AND`, and `OR`.
* Sort query results using `ORDER BY`.
* Limit the number of returned rows using `LIMIT`.
* Rename calculated columns using `AS`.
* Predict query results before executing SQL statements.

## Tables and Datasets

The exercise uses five tables containing sample academic, employee, payroll, and project data.

| Table         | Description                                            |
| ------------- | ------------------------------------------------------ |
| `students`    | Student information, including age and department.     |
| `courses`     | Course details, departments, and credit values.        |
| `enrollments` | Student enrolments in courses and the grades received. |
| `salaries`    | Employee salaries, bonuses, and departments.           |
| `projects`    | Project names, departments, and allocated budgets.     |

## Queries Covered

The 15 questions focus on the following tasks:

### 1. Students

* Retrieve distinct departments.
* Calculate average student age per department.
* Find departments with more than one student.
* Filter students by an age range.
* Combine department and age conditions.

### 2. Courses

* Calculate total credits per department and filter grouped results.
* Find courses that do not have four credits.
* Retrieve the three courses with the highest credit values.

### 3. Enrollments

* Calculate maximum, minimum, and average grades.
* Count enrolments per course.

### 4. Salaries

* Calculate total salary and bonus per department.
* Find departments with an average salary above a specified amount.
* Calculate total compensation by adding salary and bonus.

### 5. Projects

* Calculate total and average project budgets per department.
* Filter projects by budget range while excluding Marketing.

## SQL Concepts Practised

### Aggregate Functions

Aggregate functions summarise multiple rows into useful values.

```sql
SELECT
    MAX(grade) AS max_grade,
    MIN(grade) AS min_grade,
    AVG(grade) AS avg_grade
FROM enrollments;
```

### GROUP BY

`GROUP BY` combines rows with matching values so aggregate functions can calculate results for each group.

```sql
SELECT department, AVG(age) AS avg_age
FROM students
GROUP BY department;
```

### HAVING

`HAVING` filters groups after aggregation.

```sql
SELECT department, COUNT(*) AS student_count
FROM students
GROUP BY department
HAVING COUNT(*) > 1;
```

### BETWEEN

`BETWEEN` checks whether a value falls within a specified range.

```sql
SELECT *
FROM students
WHERE age BETWEEN 21 AND 23;
```

### Calculated Columns and Aliases

SQL can perform calculations and use `AS` to give the resulting column a meaningful name.

```sql
SELECT
    employee_id,
    name,
    salary,
    bonus,
    salary + bonus AS total_compensation
FROM salaries;
```

## Key Learning

This exercise helps me develop a better understanding of how SQL can be used not only to retrieve individual records but also to summarise and compare data.

I am practising the difference between filtering individual rows with `WHERE` and filtering grouped results with `HAVING`. I am also learning how aggregate functions and calculated columns can turn raw data into information that is easier to interpret.

## Exercise Format

The original assignment is designed as a handwritten, pen-and-paper activity. Each question requires writing the SQL query and drawing the expected output table, using the exact column names specified in the brief.

## Course Information

* **Course:** BrightLearn Data Analytics
* **Module:** SQL Fundamentals
* **Exercise:** 02
* **Topic:** SQL Aggregate Functions & Operators
* **Exercise format:** Handwritten SQL queries and expected output tables

## Repository Purpose

This repository forms part of my Data Analytics learning journey. It documents my progress in SQL, from basic data retrieval and filtering to aggregation, grouping, and more advanced conditions.

**Status:** SQL Fundamentals – Exercise 2
