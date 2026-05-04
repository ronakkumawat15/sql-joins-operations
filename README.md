# 📊 SQL Project: Multi-Table Operations & Joins

##  Description

This project demonstrates advanced SQL techniques for working with multiple tables using joins, subqueries, and data integration. It focuses on building real-world queries that combine data from different sources to generate meaningful insights.

---

##  Objective

To perform complex data analysis by joining multiple tables and handling relational data efficiently.

---

##  Tools Used

* MySQL
* SQL

---

##  Dataset

This project uses the **Employees Sample Database**:

* `employees` (300k+ records)
* `departments` (9 records)
* `dept_emp` (department assignments)
* `salaries` (2.8M+ records)
* `titles` (job history)

---

##  Key Concepts Covered

* INNER JOIN (matching records)
* LEFT JOIN (optional relationships)
* UNION / UNION ALL
* Correlated Subqueries
* DISTINCT for duplicate handling
* Conditional aggregation
* Query optimization (INDEX, EXPLAIN)

---

## Project Structure

```id="1q7ldv"
sql-joins-operations/
│
├── README.md
├── queries/
│   ├── inner_join.sql
│   ├── left_join.sql
│   ├── union.sql
│   ├── subquery.sql
│   ├── distinct_titles.sql
│   ├── gender_ratio.sql
│   ├── optimization.sql
│
├── documentation/
│   └── explanation.md
│
└── outputs/
    ├── join_result.png
    ├── subquery_result.png
```

---

## Reports & Queries

###  Employee-Department Mapping (INNER JOIN)

* Combines employees with their departments
* Filters only current assignments

### Employees with Manager Info (LEFT JOIN)

* Retrieves employee and manager relationships
* Handles missing data using LEFT JOIN

###  Active vs Former Employees (UNION)

* Combines datasets into a single result
* Uses UNION ALL for performance

###  Current Salary (Correlated Subquery)

* Fetches salary per employee dynamically
* Demonstrates subquery usage inside SELECT

###  Unique Job Titles (DISTINCT)

* Removes duplicate job titles
* Filters only current records

###  Department Gender Ratio

* Uses conditional aggregation
* Calculates percentage of male and female employees

---

##  Sample Query

```sql id="qbxm9c"
SELECT e.emp_no,
CONCAT(e.first_name, ' ', e.last_name) AS name,
d.dept_name
FROM employees e
JOIN dept_emp de ON e.emp_no = de.emp_no
JOIN departments d ON de.dept_no = d.dept_no
WHERE de.to_date > CURDATE();
```

---

## Performance Optimization

* Used indexing to improve query speed
* Applied filtering early to reduce join workload
* Used EXPLAIN ANALYZE to evaluate performance

---

##  Skills Gained

* Multi-table data integration
* Writing efficient JOIN queries
* Handling NULL values in relationships
* Query performance tuning

---

##  Key Learnings

* INNER JOIN returns only matching records
* LEFT JOIN includes unmatched records
* Proper join conditions prevent Cartesian products
* Early filtering improves performance by 60–90%

---

##  Common Mistakes Avoided

* Missing JOIN conditions (Cartesian product)
* Incorrect UNION column mismatch
* Ignoring NULL values
* Inefficient queries on large datasets

---

##  Conclusion

This project demonstrates practical SQL skills required for data engineering and analytics roles. It strengthens understanding of relational databases and prepares for advanced data operations.
