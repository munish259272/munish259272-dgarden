---
{"dg-publish":true,"permalink":"/learning/programming/python/practice/interview-questions/boa/q-and-a/sql-questions/","dg-note-properties":{}}
---


# Pre Code 
```bash{pre}
export PGHOST=localhost
export PGUSER=postgres
export PGDATABASE=postgres
export PDPASSWORD="mukesh"

psql -q -c "
-- Drop the table if it already exists (optional, for clean practice)
DROP TABLE IF EXISTS empsalary;

-- Create the table
CREATE TABLE empsalary (
    depname  TEXT,
    empno    INTEGER,
    salary   NUMERIC
);

-- Optional: add a primary key if you want (not required for window function practice)
-- ALTER TABLE empsalary ADD PRIMARY KEY (empno);

INSERT INTO empsalary (depname, empno, salary) VALUES
    ('sales',   11, 5200),
    ('sales',    1, 5000),
    ('sales',    2, 4800),
    ('IT',       5, 8000),
    ('IT',       4, 7700),
    ('IT',       3, 6000),
    ('support',  7, 4200),
    ('support',  6, 4100);
    
DROP TABLE IF EXISTS departments;

CREATE TABLE departments (
    dept_code   TEXT PRIMARY KEY,          -- e.g. 'sales', 'IT'
    dept_name   TEXT NOT NULL,
    manager     TEXT,
    location    TEXT
);

INSERT INTO departments (dept_code, dept_name, manager, location) VALUES
    ('sales',   'Sales & Marketing',    'Sarah Jain',    'Chennai'),
    ('IT',      'Information Technology','Raj Patel',     'Bangalore'),
    ('support', 'Customer Support',     'Priya Menon',   'Hyderabad'),
    ('hr',      'Human Resources',      'Anil Kumar',    'Mumbai');     -- extra dept with no employees
" > /dev/null
```


## Tables
> [!Multi-Column]
> > [!g-white|wide-1] empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2] departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |
> 

How to make the fist column take more width.
# constraints in SQL (psql)

In SQL (specifically PostgreSQL), **constraints** are rules applied to columns or tables to ensure the accuracy and reliability of the data. They act as the "guardrails" for your database.

If you try to insert or update data that violates a constraint, PostgreSQL will throw an error and block the transaction.

---
dg-publish: true

## 1. Primary Key (`PRIMARY KEY`)

A Primary Key uniquely identifies each row in a table. It is actually a combination of **NOT NULL** and **UNIQUE**.

- **Rule:** It must contain unique values, and it cannot contain `NULL` values.
    
- **Limit:** Only **one** Primary Key is allowed per table.
    
```sql
CREATE TABLE users (
    user_id INT PRIMARY KEY,
    username TEXT
);
```

## 2. Foreign Key (`FOREIGN KEY`)

A Foreign Key ensures "referential integrity." It links a column in one table to the Primary Key of another table.

- **Rule:** You cannot add a value to the child table if it doesn't exist in the parent table.

```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    user_id INT REFERENCES users(user_id) -- This is the Foreign Key
);
```

## 3. Unique (`UNIQUE`)

This ensures that all values in a column are different from one another.

- **Difference from PK:** You can have multiple `UNIQUE` columns in one table, and (unlike Primary Keys) they _can_ accept `NULL` values (unless you also add `NOT NULL`).
    

## 4. Not Null (`NOT NULL`)

This is the most common constraint. It prevents a column from ever having a `NULL` value.

- **Use case:** Essential for fields like "Email" or "Password" where the data is mandatory.
    

## 5. Check (`CHECK`)

This is a powerful constraint that allows you to define a custom logical expression that every row must satisfy.

- **Example:** Ensuring a price is always positive or an age is over 18.
    
```sql
CREATE TABLE products (
    price NUMERIC CHECK (price > 0),
    discounted_price NUMERIC,
    CHECK (discounted_price < price) -- Table-level check
);
```

## 6. Default (`DEFAULT`)

While not strictly a "constraint" that blocks data, it provides a fallback value if no value is specified during an `INSERT`.

```sql
CREATE TABLE profile (
    status TEXT DEFAULT 'active'
);
```

---

## 7. Exclusion (`EXCLUDE`)

A specialized PostgreSQL constraint. It ensures that if any two rows are compared on specified columns using specified operators, at least one of these operator comparisons will return false.

- **Common use:** Preventing overlapping date ranges in a booking system.
    

---

### Summary Table

|**Constraint**|**Main Purpose**|**Can be NULL?**|**Multiple per table?**|
|---|---|---|---|
|**PRIMARY KEY**|Unique ID for the row|No|No (Only 1)|
|**FOREIGN KEY**|Links to another table|Yes|Yes|
|**UNIQUE**|Prevents duplicates|Yes|Yes|
|**NOT NULL**|Forces a value to exist|No|Yes|
|**CHECK**|Logical validation|Yes|Yes|

---

### Pro-Tip: Column vs. Table Level

You can define constraints on a single column (as shown above) or at the **Table Level**. Table-level constraints are necessary if the rule involves **multiple columns** (e.g., `PRIMARY KEY (order_id, item_id)`).

**Would you like to see how to add a constraint to a table that has already been created using `ALTER TABLE`?**



# map columns from one table to another table(same location)

In SQL, "mapping" columns from one table to another usually refers to one of two things: **linking** them for a query (using `JOIN`) or **moving/copying** data from one table to another.

Here is how you handle both scenarios in PostgreSQL.

---

## 1. Linking Tables (The `JOIN` Mapping)

If you want to view columns from Table A and Table B together because they share a common ID, you use a `JOIN`. This doesn't move data; it just maps the relationship for the result.

```sql
SELECT 
    users.username, 
    orders.order_date
FROM users
JOIN orders ON users.user_id = orders.user_id;
```

- **The Map:** `users.user_id` $\rightarrow$ `orders.user_id`.
    

---

## 2. Copying Data (The `INSERT INTO ... SELECT` Mapping)

If you need to move data from a "Staging" table to a "Production" table, you map the columns explicitly in an `INSERT` statement.

```sql
INSERT INTO production_users (full_name, contact_email)
SELECT name, email
FROM staging_users;
```

- **The Map:** `name` becomes `full_name`, and `email` becomes `contact_email`.
    
- **Note:** The data types must match or be compatible.


> [!question]- In this case the number of rows in the target table should be equal to or greater than the source table ?
> 
> Actually, no—the number of rows currently in the target table doesn't matter at all!
> 
> When you use `INSERT INTO ... SELECT`, you are **adding new rows** to the target table, not filling in empty spots. It's like adding new pages to a book rather than writing in the margins of existing pages.
> 
> ---
> 
> ### 1. How it works
> 
> - If the target table is **empty**, it will now have exactly as many rows as your `SELECT` statement produced.
>     
> - If the target table **already has 1,000 rows** and your `SELECT` produces 50 rows, the target table will now have **1,050 rows**.
>     
> 
> ---
> 
> ### 2. The "Mapping" Constraints
> 
> While the **row count** doesn't matter, two other things must be "equal":
> 
> 1. **Column Count:** The number of columns you select must match the number of columns you are inserting into.
>     
> 2. **Data Types:** The data types must be compatible. You can't map a `TEXT` column from the source into an `INTEGER` column in the target without casting it.
>     
> 
> SQL
> 
> ```
> -- This works even if 'target_table' is empty
> INSERT INTO target_table (col1, col2)
> SELECT source_col1, source_col2 
> FROM source_table;
> ```
> 
> ---
> 
> ### 3. What if you want to update existing rows instead?
> 
> If your goal was to "map" data onto rows that **already exist** (matching them by an ID), then you wouldn't use `INSERT`. You would use an **`UPDATE`** with a join logic:
> 
> SQL
> 
> ```
> UPDATE target_table
> SET target_col = source_table.source_col
> FROM source_table
> WHERE target_table.id = source_table.id;
> ```
> 
> In this `UPDATE` scenario, if the source has 100 rows but the target only has 50 matching IDs, only those 50 rows will be updated.
> 
> ---
> 
> ### Summary
> 
> - **`INSERT INTO ... SELECT`**: Always **increases** the row count of the target table.
>     
> - **`UPDATE ... FROM`**: Keeps the row count the same but **changes the values** of existing rows.
>     
> 
> **Would you like to see how to handle a "Conflict" (UPSERT), where you insert a row if it's new but update it if the ID already exists?**

---

## 3. Creating a New Table from an Old One

If you want to create a new table and map all the data into it immediately, use `CREATE TABLE AS`.

```sql
CREATE TABLE user_backups AS 
SELECT user_id, username 
FROM users;
```

---

## 4. Mapping with Logic (`CASE` Statement)

Sometimes the mapping isn't 1-to-1. You might need to transform the data while mapping it. For example, mapping a numerical status to a text label:

```sql
SELECT 
    order_id,
    CASE 
        WHEN status_code = 1 THEN 'Pending'
        WHEN status_code = 2 THEN 'Shipped'
        ELSE 'Unknown'
    END AS status_text
FROM orders;
```

---

### Which one fits your situation?

|**If you want to...**|**Use this method**|
|---|---|
|**View** data from two tables together|`JOIN`|
|**Move** data into an existing table|`INSERT INTO ... SELECT`|
|**Sync/Update** specific columns|`UPDATE ... FROM`|
|**Transform** values during mapping|`CASE` statements|

---

### Pro-Tip: The `UPDATE ... FROM` Mapping

If you want to update columns in `Table A` based on values in `Table B`:

```sql
UPDATE table_a
SET email = table_b.new_email
FROM table_b
WHERE table_a.user_id = table_b.user_id;
```

**Would you like me to explain how to use a "Foreign Key" to enforce this mapping so the data stays consistent automatically?**



# map columns from one table to another table(different location/server)

Yes, absolutely! Depending on whether you are working in **Python** or **SQL**, the concept of a "dictionary" for mapping data across different locations is a very common architecture.

Here are the three most common ways to handle mapping when your source and target are separated (e.g., different databases, different files, or different servers).

---

## 1. The Python Dictionary (The "In-Memory" Map)

If your target is a file or an API, and your source is a database, you can use a Python dictionary as a **Translation Layer**.

**The Scenario:** You have a "Department ID" in your database, but your target system needs the "Department Name."


```python
# The 'Dictionary' acts as the mapping reference
dept_mapping = {
    101: "Engineering",
    102: "Marketing",
    103: "Sales"
}

# Source data (perhaps from a CSV or DB)
source_data = [{"id": 1, "dept_id": 101}, {"id": 2, "dept_id": 102}]

# Mapping to the target
for row in source_data:
    # We 'map' the ID to the Name using the dictionary
    row["dept_name"] = dept_mapping.get(row["dept_id"], "Unknown")
```

---

## 2. The "Lookup Table" (The SQL Map)

In database design, we often create a **Lookup Table** (which is essentially a database version of a dictionary). This is used when the "Mapping" lives in the database, but the "Target" might be a report or a different schema.

**How it looks:**

- **Table A (Orders):** Contains `status_code` (1, 2, 3).
    
- **Table B (Status_Dict):** Contains the mapping (`1` = 'Pending', `2` = 'Shipped').
    

You map them together using a `JOIN`. Even if the target is a different database, you can use **Foreign Data Wrappers (FDW)** in PostgreSQL to treat a remote table like a local dictionary.

> [!question]- I do not understand this, please explain.
> 
> # Understanding Lookup Tables (The "SQL Dictionary")
> 
> Let me explain this concept in a simpler way with a concrete example.
> 
> ## **What is a Lookup Table?**
> 
> Think of a lookup table as a **dictionary that lives in your database**. Instead of having hardcoded values like `101 = "Engineering"` in your Python code, you store these mappings in a database table.
> 
> ## **Real-World Example**
> 
> Imagine you have two tables:
> 
> ### **1. Orders Table** (Main data)
> ```
> | order_id | customer_id | status_code |
> |----------|-------------|-------------|
> | 1001     | 55          | 1           |
> | 1002     | 78          | 2           |
> | 1003     | 55          | 3           |
> ```
> 
> You can see `status_code` but you don't know what 1, 2, or 3 mean!
> 
> ### **2. Status Dictionary Table** (Lookup table)
> ```
> | status_code | status_name | description          |
> |-------------|-------------|----------------------|
> | 1           | Pending     | Order is being processed |
> | 2           | Shipped     | Order has been shipped  |
> | 3           | Delivered   | Order has been delivered|
> ```
> 
> ## **How They Connect (The JOIN)**
> 
> Here's the SQL that acts like your Python dictionary:
> 
> ```sql
> SELECT 
>     o.order_id,
>     o.customer_id,
>     o.status_code,
>     s.status_name,  -- This is the mapped value!
>     s.description
> FROM orders o
> JOIN status_dict s ON o.status_code = s.status_code;
> ```
> 
> **Result:**
> ```
> | order_id | customer_id | status_code | status_name | description          |
> |----------|-------------|-------------|-------------|----------------------|
> | 1001     | 55          | 1           | Pending     | Order is being processed |
> | 1002     | 78          | 2           | Shipped     | Order has been shipped  |
> | 1003     | 55          | 3           | Delivered   | Order has been delivered|
> ```
> 
> ## **Why Use Lookup Tables?**
> 
> 1. **Single Source of Truth**: Change "Pending" to "Processing" in one place
> 2. **Data Integrity**: Can't enter status_code = 4 unless it's defined in lookup
> 3. **Multi-language support**: Could have another lookup for Spanish names
> 4. **Easier maintenance**: No hardcoded values in your application code
> 
> ## **Different Database/Server Scenario**
> 
> If your lookup table is on a different server:
> 
> ### **PostgreSQL with Foreign Data Wrapper (FDW):**
> ```sql
> -- Step 1: Create connection to remote server
> CREATE SERVER remote_server FOREIGN DATA WRAPPER postgres_fdw;
> 
> -- Step 2: Create foreign table (acts like local table but data is remote)
> CREATE FOREIGN TABLE remote_status_dict (
>     status_code INT,
>     status_name VARCHAR(50)
> ) SERVER remote_server;
> 
> -- Step 3: Use it in JOIN like a local table!
> SELECT o.*, rs.status_name
> FROM local_orders o
> JOIN remote_status_dict rs ON o.status_code = rs.status_code;
> ```
> 
> ### **SQL Server with Linked Server:**
> ```sql
> SELECT o.*, rs.status_name
> FROM local_orders o
> JOIN [RemoteServer].[Database].[Schema].[status_dict] rs 
>     ON o.status_code = rs.status_code;
> ```
> 
> ## **Comparison: Python vs SQL**
> 
> | Aspect | Python Dictionary | SQL Lookup Table |
> |--------|-------------------|------------------|
> | **Location** | In application memory | In database |
> | **Persistence** | Lost when app restarts | Permanent storage |
> | **Sharing** | Only this app can use it | Any app/database user can use it |
> | **Performance** | Very fast (in-memory) | Needs disk I/O, but can be indexed |
> | **Best for** | Small, rarely changing data | Large, shared, frequently updated mappings |
> 
> ## **Simple Analogy**
> 
> - **Python dictionary** = Post-it note on your desk with phone numbers
> - **SQL lookup table** = Company-wide phone directory that everyone can access and update
> 
> Would you like me to explain any part of this in more detail or show you specific examples for your database system?

---

## 3. Mapping Files (JSON / YAML)

When the target is in a completely different location (like a different server or cloud bucket), developers often use a **Configuration File** as a dictionary.

- **Mapping File (`map.json`):**
    
    JSON
    
    ```
    {
      "legacy_system_id": "new_cloud_id",
      "A10": "USR_990",
      "B20": "USR_991"
    }
    ```
    

The Python script reads this "dictionary" first, then processes the data from the source location and sends it to the target location.

---

## 4. Why use a Dictionary for mapping?

Using a dictionary/lookup table instead of "hard-coding" the mapping is better because:

1. **Decoupling:** You can change the mapping (e.g., change "Sales" to "Revenue Ops") without changing your actual code.
    
2. **Location Independence:** Your code can stay in one place, your source in another, and your "dictionary" can act as the bridge.
    
3. **Speed:** Looking up a value in a Python dictionary is **$O(1)$** (constant time), making it extremely fast for large data migrations.
    

---

### Summary of Mapping Tools

|**Location of Target**|**Best "Dictionary" Tool**|
|---|---|
|**Same Database**|Lookup Table + `JOIN`|
|**Different Database**|Foreign Data Wrappers (FDW) or ETL Tool|
|**API / File / External**|Python `dict` or JSON Mapping File|

**Would you like to see how to load a JSON file into a Python dictionary to use it as a mapper for a large CSV file?**


# top or limit

Yes! PostgreSQL has several ways to limit data output. Here are the main methods:

## **1. LIMIT (Most Common)**
```sql
-- Get only 10 rows
SELECT * FROM users LIMIT 10;

-- Get 10 rows starting from the 5th row (skips first 4)
SELECT * FROM users LIMIT 10 OFFSET 4;
```

## **2. FETCH FIRST (ANSI SQL Standard)**
```sql
-- Get first 10 rows
SELECT * FROM users FETCH FIRST 10 ROWS ONLY;

-- Get first 10% of rows
SELECT * FROM users FETCH FIRST 10 PERCENT ROWS ONLY;
```

## **3. Window Functions (for Ranking/Limiting Groups)**
```sql
-- Get top 3 highest salaries in each department
SELECT * FROM (
  SELECT *,
    ROW_NUMBER() OVER (PARTITION BY department_id ORDER BY salary DESC) as rank
  FROM employees
) ranked
WHERE rank <= 3;
```

## **4. psql Client Commands (Interactive Terminal)**

When you're in the `psql` command-line interface, you can use these special commands:

```sql
-- Show only first few rows in results (doesn't affect the query)
\pset pager off  -- Disable pager to see all output at once
\pset format wrapped  -- Wrap long lines

-- Or use \x for expanded display (vertical format)
\x auto  -- Auto-switch to vertical for wide results
```

## **5. Common Use Cases**

### **Top N Results by Column**
```sql
-- Top 5 highest paid employees
SELECT * FROM employees 
ORDER BY salary DESC 
LIMIT 5;

-- Top 10% most recent orders
SELECT * FROM orders
ORDER BY order_date DESC
FETCH FIRST 10 PERCENT ROWS ONLY;
```

### **Pagination**
```sql
-- Page 1: Rows 1-10
SELECT * FROM products LIMIT 10 OFFSET 0;

-- Page 2: Rows 11-20  
SELECT * FROM products LIMIT 10 OFFSET 10;

-- Page 3: Rows 21-30
SELECT * FROM products LIMIT 10 OFFSET 20;
```

## **6. Performance Tips**

```sql
-- Add ORDER BY for consistent results (otherwise order is unpredictable)
SELECT * FROM users ORDER BY id LIMIT 10;

-- Be careful with OFFSET on large tables (it's inefficient)
-- Better to use WHERE clause for deep pagination:
SELECT * FROM users 
WHERE id > 1000  -- Last ID from previous page
ORDER BY id 
LIMIT 10;
```

## **7. psql Display Settings**
```bash
# Set display limit when starting psql
psql "dbname=mydb" --pset="pager=off" -c "SELECT * FROM large_table"

# In psql, set environment variables
\setenv PAGER less
\setenv LESS '-iMFXSx4R'
```

## **Key Differences:**
- **LIMIT** - PostgreSQL specific (also works in MySQL, SQLite)
- **FETCH FIRST** - ANSI SQL standard (works in Oracle, DB2, newer SQL Server)
- **TOP** - SQL Server/Sybase specific (doesn't work in PostgreSQL)

## **Quick Reference:**
```sql
-- PostgreSQL/MY SQL/SQLite way:
SELECT * FROM table LIMIT 10;

-- Standard SQL way (works in PostgreSQL):
SELECT * FROM table FETCH FIRST 10 ROWS ONLY;

-- SQL Server way (does NOT work in PostgreSQL):
-- SELECT TOP 10 * FROM table;  -- ERROR in PostgreSQL!
```

**Most PostgreSQL developers use `LIMIT`** as it's concise and widely understood, even though `FETCH FIRST` is the SQL standard.

Would you like to see examples of any specific limiting scenario?


# Subquery

## What Is a Subquery in SQL (PostgreSQL)?

A **subquery** is a **query nested inside another SQL query**.  
It is used when the result of one query is needed as an **input** to another query.

In PostgreSQL (psql), subqueries are fully supported and are commonly used in `SELECT`, `WHERE`, `FROM`, and `HAVING` clauses.

---

## Simple Definition

> A subquery is an **inner query** whose result is consumed by an **outer query**.

---

## Basic Example

```sql
SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);
```

### What happens here

1. Inner query computes the average salary
    
2. Outer query compares each employee’s salary against that value
    

The inner query runs **first**, then its result is passed to the outer query.

---

## Types of Subqueries (Very Important)

### 1. Scalar Subquery (Returns a Single Value)

Returns **one row, one column**.

```sql
SELECT name,
       (SELECT COUNT(*) FROM orders) AS total_orders
FROM customers;
```

Use cases:

- Comparisons (`=`, `>`, `<`)
    
- Assigning computed values
    

---

### 2. Single-Row Subquery

Returns **one row but multiple columns**.

```sql
SELECT *
FROM orders
WHERE (customer_id, order_date) = (
    SELECT customer_id, MAX(order_date)
    FROM orders
    GROUP BY customer_id
);
```

---

### 3. Multi-Row Subquery

Returns **multiple rows** (one column).

```sql
SELECT *
FROM customers
WHERE id IN (
    SELECT customer_id
    FROM orders
);
```

Common operators:

- `IN`
    
- `ANY`
    
- `ALL`
    

---

### 4. Correlated Subquery (Most Confusing, Most Powerful)

A **correlated subquery** depends on values from the outer query and runs **once per row**.

```sql
SELECT c.name
FROM customers c
WHERE EXISTS (
    SELECT 1
    FROM orders o
    WHERE o.customer_id = c.id
);
```

Key point:

- Inner query cannot run independently
    
- It references `c.id` from the outer query
    

---

### 5. Subquery in FROM Clause (Derived Table)

The subquery acts like a **temporary table**.

```sql
SELECT dept, avg_salary
FROM (
    SELECT department AS dept,
           AVG(salary) AS avg_salary
    FROM employees
    GROUP BY department
) t
WHERE avg_salary > 60000;
```

---

## Subquery vs JOIN (Critical Comparison)

|Aspect|Subquery|JOIN|
|---|---|---|
|Readability|Often clearer|Can be verbose|
|Performance|Sometimes slower|Often faster|
|Correlation|Supported|Not needed|
|Optimization|PostgreSQL may rewrite|Usually optimized|

### Important PostgreSQL Note

PostgreSQL’s optimizer often **rewrites subqueries into joins**, so performance differences are smaller than in older databases.

---

## When to Use Subqueries

Use subqueries when:

- You need a **step-by-step logical filter**
    
- The result depends on aggregated data
    
- The logic reads more clearly as nested operations
    
- You need `EXISTS` / `NOT EXISTS`
    

Avoid subqueries when:

- A simple `JOIN` is clearer
    
- The subquery is correlated and slow
    
- You can pre-aggregate and join instead
    

---

## Execution Order (Conceptual)

1. Subquery executes
    
2. Result is materialized or streamed
    
3. Outer query consumes result
    

(Actual execution is optimizer-dependent, but this model is correct for reasoning.)

---

## Common Interview Pitfall

**Wrong:**

```sql
SELECT *
FROM orders
WHERE total > (
    SELECT total
    FROM orders
);
```

This fails because the subquery returns **multiple rows**.

**Correct:**

```sql
WHERE total > ALL (
    SELECT total
    FROM orders
);
```

---

## Summary

- A subquery is a **query inside another query**
    
- Used to feed results into an outer query
    
- Can return:
    
    - One value
        
    - One row
        
    - Multiple rows
        
- Can be **correlated** or **non-correlated**
    
- PostgreSQL optimizes many subqueries into joins
    

---

If you want, I can next:

- Rewrite subqueries into **JOIN equivalents**
    
- Explain **EXISTS vs IN**
    
- Show **performance pitfalls**
    
- Walk through **execution plans (`EXPLAIN`)**
    

Just tell me.


# view and stored procedure ![[view vs stored procedure.mp4]]

### What is a **View** in PostgreSQL (SQL)?

A **View** is a **virtual table** that is based on the result of a `SELECT` query. It does not store data physically (except in the case of **materialized views**), but it shows the data as if it were a real table.

You can query a view exactly like a normal table.

#### Why use Views?
- Simplify complex queries (hide JOINs, calculations, etc.)
- Provide security (show only certain columns or rows to users)
- Present data in a different format without duplicating it
- Abstract the underlying schema

#### Syntax to create a View

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

#### Example

Suppose you have these tables:

```sql
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name TEXT,
    salary NUMERIC,
    department_id INTEGER
);

CREATE TABLE departments (
    id SERIAL PRIMARY KEY,
    dept_name TEXT
);
```

Create a view that shows employee names with their department:

```sql
CREATE VIEW employee_dept_view AS
SELECT 
    e.name,
    e.salary,
    d.dept_name
FROM employees e
JOIN departments d ON e.department_id = d.id
WHERE e.salary > 50000;
```

Now you can query it like a table:

```sql
SELECT * FROM employee_dept_view;
```

#### Types of Views in PostgreSQL
1. **Regular View** (above example) → Not stored physically, query is re-executed every time.
2. **Materialized View** → Stores the result physically (faster, but data can become stale).

```sql
CREATE MATERIALIZED VIEW mat_employee_dept AS
SELECT ... same query ...;

-- To update data later
REFRESH MATERIALIZED VIEW mat_employee_dept;
```

#### Key Points about Views
- You can sometimes `INSERT`, `UPDATE`, or `DELETE` through a view (only if it maps 1:1 to a single table and meets certain rules).
- Views can be dropped: `DROP VIEW view_name;`


> [!question]- We know that updating a view in dataframe updates the original dataframe, does the same happens when we update a view in psql ?
> 
> No — **PostgreSQL views do NOT behave like DataFrame views by default**.
> 
> This is an important conceptual distinction.
> 
> You’re probably thinking in terms of pandas / Spark DataFrames, where a “view” can be a reference to the same underlying memory. SQL views are not memory references — they are **stored query definitions**.
> 
> ---
> 
> # 🔎 What Happens When You Update a View in PostgreSQL?
> 
> It depends on the type of view.
> 
> ---
> 
> ## 1️⃣ Regular View (Non-Materialized View)
> 
> A regular view is just a saved `SELECT` statement.
> 
> ```sql
> CREATE VIEW v AS
> SELECT * FROM employees;
> ```
> 
> When you run:
> 
> ```sql
> SELECT * FROM v;
> ```
> 
> PostgreSQL rewrites it internally as:
> 
> ```sql
> SELECT * FROM employees;
> ```
> 
> ### 🔁 If You UPDATE Through the View
> 
> ```sql
> UPDATE v
> SET salary = 80000
> WHERE id = 1;
> ```
> 
> If the view is **updatable**, then:
> 
> ✔ The update **modifies the underlying base table** (`employees`)  
> ✔ Because the view does not store data — it only forwards operations
> 
> ---
> 
> ## 🚨 BUT — Not All Views Are Updatable
> 
> A view is automatically updatable **only if**:
> 
> - It references **one single table**
>     
> - No `JOIN`
>     
> - No `GROUP BY`
>     
> - No `DISTINCT`
>     
> - No aggregates
>     
> - No set operations (`UNION`, etc.)
>     
> 
> ### ❌ Your Earlier Example Is NOT Updatable
> 
> ```sql
> CREATE VIEW employee_dept_view AS
> SELECT 
>     e.name,
>     e.salary,
>     d.dept_name
> FROM employees e
> JOIN departments d ON e.department_id = d.id;
> ```
> 
> This contains a `JOIN`.
> 
> If you try:
> 
> ```sql
> UPDATE employee_dept_view
> SET salary = 90000
> WHERE name = 'John';
> ```
> 
> PostgreSQL will throw:
> 
> ```
> ERROR: cannot update view
> DETAIL: Views that do not select from a single table are not automatically updatable.
> ```
> 
> Unless you define an `INSTEAD OF` trigger.
> 
> ---
> 
> ## 2️⃣ Materialized View
> 
> A materialized view **stores data physically**.
> 
> ```sql
> CREATE MATERIALIZED VIEW mv AS
> SELECT * FROM employees;
> ```
> 
> If you run:
> 
> ```sql
> UPDATE mv SET salary = 90000;
> ```
> 
> ❌ You cannot update it directly.
> 
> Materialized views are **read-only**.
> 
> To reflect base table changes:
> 
> ```sql
> REFRESH MATERIALIZED VIEW mv;
> ```
> 
> ---
> 
> # 🔬 Comparison: DataFrame View vs PostgreSQL View
> 
> |Feature|DataFrame View|PostgreSQL View|
> |---|---|---|
> |Stores data?|Usually shares memory|No|
> |Update reflects base?|Yes (often)|Only if updatable|
> |Query re-executed each time?|No|Yes|
> |Can become stale?|No|Only materialized views|
> 
> ---
> 
> # 🧠 Mental Model
> 
> Think of a PostgreSQL regular view as:
> 
> > A macro or query rewrite rule — not a memory reference.
> 
> When you query a view, PostgreSQL’s planner expands it into the original query before execution.
> 
> ---
> 
> # 🎯 Direct Answer to Your Question
> 
> > Does updating a view update the original table?
> 
> ✔ **Yes — but only if the view is automatically updatable.**
> 
> Otherwise:
> 
> - ❌ It fails
>     
> - OR requires `INSTEAD OF` triggers
>     
> - Materialized views cannot be updated directly
>     
> 
> ---
> 
> If you'd like, I can also explain how PostgreSQL internally rewrites views in the query planner — that part is quite elegant and aligns well with your interest in query execution mechanics.

---

### What is a **Stored Procedure** in PostgreSQL?

A **Stored Procedure** is a pre-compiled collection of SQL (and procedural) statements that are stored in the database and can be executed repeatedly.

PostgreSQL uses the language **PL/pgSQL** (Procedural Language/PostgreSQL) by default for stored procedures.

#### Why use Stored Procedures?
- Encapsulate business logic on the server side
- Reduce network traffic (send only procedure name + parameters)
- Improve performance (pre-parsed and planned)
- Centralize logic (easier maintenance and security)

#### Syntax (PostgreSQL uses `CREATE FUNCTION` for what other databases call "stored procedures")

```sql
CREATE OR REPLACE FUNCTION procedure_name(param1 TYPE, param2 TYPE)
RETURNS return_type AS $
BEGIN
    -- Your SQL and logic here
END;
$ LANGUAGE plpgsql;
```

Note: In PostgreSQL, there is no separate `CREATE PROCEDURE` until **PostgreSQL 11+**, where it was added for compatibility.

#### Example: Stored Procedure to give a raise to employees in a department

**Using `CREATE FUNCTION` (works in all versions):**

```sql
CREATE OR REPLACE FUNCTION give_raise_to_dept(dept_id INTEGER, percentage NUMERIC)
RETURNS VOID AS $
BEGIN
    UPDATE employees
    SET salary = salary * (1 + percentage / 100)
    WHERE department_id = dept_id;

    RAISE NOTICE 'Raise applied to department %', dept_id;
END;
$ LANGUAGE plpgsql;
```

Call it:

```sql
SELECT give_raise_to_dept(10, 15);  -- 15% raise to department 10
```

**Using `CREATE PROCEDURE` (PostgreSQL 11 and later):**

```sql
CREATE OR REPLACE PROCEDURE give_raise_to_dept_proc(dept_id INTEGER, percentage NUMERIC)
LANGUAGE plpgsql
AS $
BEGIN
    UPDATE employees
    SET salary = salary * (1 + percentage / 100)
    WHERE department_id = dept_id;

    COMMIT;  -- Optional, depending on transaction control
END;
$;
```

Call it (note the difference):

```sql
CALL give_raise_to_dept_proc(10, 15);
```

#### Key Differences: FUNCTION vs PROCEDURE in PostgreSQL

| Feature                  | FUNCTION (`CREATE FUNCTION`)               | PROCEDURE (`CREATE PROCEDURE` – v11+)      |
|--------------------------|--------------------------------------------|--------------------------------------------|
| Can return a value       | Yes (via RETURNS)                          | No (only VOID or uses OUT parameters)      |
| How to call              | `SELECT function_name(...)`                | `CALL procedure_name(...)`                 |
| Can be used in SELECT    | Yes                                        | No                                         |
| Transaction control      | Cannot COMMIT/ROLLBACK inside              | Can COMMIT/ROLLBACK (useful for autonomy)  |
| Best for                 | Calculations, returning data               | Side effects (INSERT/UPDATE/DELETE)        |

---

### Quick Comparison: View vs Stored Procedure

| Feature              | View                              | Stored Procedure / Function            |
|----------------------|-----------------------------------|----------------------------------------|
| Stores data?         | No (except materialized)          | No (only executes logic)               |
| Purpose              | Present data differently          | Perform actions / business logic       |
| Can modify data?     | Limited (simple views only)       | Yes (INSERT, UPDATE, DELETE)           |
| Parameters?          | No                                | Yes                                    |
| Returns result set?  | Yes (like a table)                | Function: Yes, Procedure: No (usually) |
| Performance          | Query re-executed each time       | Pre-planned, often faster              |

Let me know if you'd like more examples (e.g., with loops, error handling in procedures, or updatable views)! 😊

# Window function

**Window functions** in PostgreSQL (and in standard SQL) are a very powerful feature that let you perform calculations **across a set of rows** that are related to the current row — **without collapsing / grouping** the rows like normal aggregate functions (`SUM()`, `AVG()`, `COUNT()`) do.

In short:

- Normal aggregates → reduce many rows → one result row
- Window functions → look at many rows → but still keep one result **per original row**

This makes them perfect for:

- Running totals / cumulative sums
- Rank / dense rank / row number within groups
- Compare row to previous/next row (lag/lead)
- Moving averages
- Percentage of total
- "Top N per group" queries
- Many analytics / reporting patterns

### Basic Syntax

```sql
<window_function>() 
OVER (
    [PARTITION BY column1, column2, ...]
    [ORDER BY columnX [ASC|DESC], ...]
    [ROWS|RANGE BETWEEN ... AND ...]    -- frame clause (optional)
) AS alias
```

- `OVER()` → turns the function into a window function
- `PARTITION BY` → like `GROUP BY`, but doesn't collapse rows (optional)
- `ORDER BY` inside OVER → defines the order inside each partition (very important for ranking, running totals, etc.)
- Frame clause (`ROWS BETWEEN` / `RANGE BETWEEN`) → defines which rows in the partition are included in the calculation (default is often from start to current row)

### Most Commonly Used Window Functions in PostgreSQL

| Function              | What it returns                              | Needs ORDER BY? | Typical use case                              |
|-----------------------|----------------------------------------------|------------------|-----------------------------------------------|
| `row_number()`        | Unique 1,2,3,... within partition            | Yes             | Sequential numbering, deduplication           |
| `rank()`              | Rank with gaps (1,1,3,…)                     | Yes             | Competition ranking                           |
| `dense_rank()`        | Rank without gaps (1,1,2,…)                  | Yes             | Ordered position without skipping             |
| `percent_rank()`      | Relative rank (0 to 1)                       | Yes             | Percentile-like ranking                       |
| `ntile(n)`            | Divides into n buckets (1 to n)              | Yes             | Quartiles, deciles                            |
| `lag(value, offset)`  | Value from previous row                      | Yes             | Difference from previous day/month            |
| `lead(value, offset)` | Value from next row                          | Yes             | Difference to next value                      |
| `first_value()`       | First value in window                        | Yes             | Show group start value on every row           |
| `last_value()`        | Last value in window                         | Yes + careful frame | Show group end value                          |
| `sum() / avg() / count()` | Running / cumulative / moving aggregates | Usually yes     | Running total, moving average                 |

### Practical Examples (using the classic `empsalary` table from PostgreSQL docs)

Assume this table:

```sql
depname  | empno | salary
---------+-------+--------
sales    |    11 |   5200
sales    |     1 |   5000
sales    |     2 |   4800
IT       |     5 |   8000
IT       |     4 |   7700
IT       |     3 |   6000
support  |     7 |   4200
support  |     6 |   4100
```

#### 1. Average salary per department (on every row)

```run-bash
psql -c "
SELECT 
    depname,
    empno,
    salary,
    AVG(salary) OVER (PARTITION BY depname) AS dept_avg
FROM empsalary;
"
```

Result:

```
depname | empno | salary | dept_avg
--------|-------|--------|----------
sales   |    11 |   5200 |     5000
sales   |     1 |   5000 |     5000
sales   |     2 |   4800 |     5000
IT      |     5 |   8000 |     7233.33
IT      |     4 |   7700 |     7233.33
...
```

> [!GROUP BY]-
> ```run-bash
> psql -c "
> SELECT 
>     depname,
>     AVG(salary) FROM empsalary
> GROUP BY depname;
> "
> ```

#### 2. Rank employees by salary within each department

```bash
psql -c "
SELECT 
    depname,
    empno,
    salary,
    RANK() OVER (PARTITION BY depname ORDER BY salary DESC) AS rank_in_dept
FROM empsalary;
"
```

Result:

```
depname | empno | salary | rank_in_dept
--------|-------|--------|--------------
sales   |    11 |   5200 |            1
sales   |     1 |   5000 |            2
sales   |     2 |   4800 |            3
IT      |     5 |   8000 |            1
IT      |     4 |   7700 |            2
IT      |     3 |   6000 |            3
```


> [!question]- All the ranks show as 1 when `ORDER BY` is removed. Does window functions `RANK()` etc need `ORDER BY DESC` or `ORDER BY ASC` to work ?
> 
> ```bash
> psql -c "
> SELECT 
>     depname,
>     empno,
>     salary,
>     RANK() OVER (PARTITION BY depname) AS rank_in_dept
> FROM empsalary;
> "
> ```
> 
> Yes, that is exactly the issue!
> 
> While `PARTITION BY` tells the window function how to **group** the data, it doesn't tell it how to **sort** it. Without an `ORDER BY` clause inside the `OVER()` parentheses, SQL treats every row in the partition as a "tie."
> 
> If everyone is tied for the same spot, they all get **Rank 1**.
> 
> ### The Fix
> 
> To make `RANK()` meaningful, you must provide an `ORDER BY`. Usually, for salaries, you want the highest earner to be Rank 1, so you use `DESC`.
> 
> 
> ```sql
> SELECT 
>     depname,
>     empno,
>     salary,
>     RANK() OVER (PARTITION BY depname ORDER BY salary DESC) AS rank_in_dept
> FROM empsalary;
> ```
> 
> ---
> 
> ### Why `ORDER BY` is Essential
> 
> Think of it like a race:
> 
> - **`PARTITION BY`**: Splits the runners into different heats (e.g., Sales vs. IT).
>     
> - **`ORDER BY`**: Determines who crossed the finish line first. Without the stopwatch (the order), the judge just shrugs and gives everyone a gold medal.
>     
> 
> ### Bonus: Difference between `RANK()` and `DENSE_RANK()`
> 
> Since you're practicing, it's worth noting how they handle ties (e.g., if two people in IT both make $8000):
> 
> |**Function**|**Behavior on Ties**|**Sequence Example**|
> |---|---|---|
> |**`ROW_NUMBER()`**|No ties allowed; unique number for every row.|1, 2, 3, 4|
> |**`RANK()`**|Ties get the same rank; **skips** the next number.|1, 1, 3, 4|
> |**`DENSE_RANK()`**|Ties get the same rank; **no gaps** in sequence.|1, 1, 2, 3|
> 
> ---
> 
> ### Quick Check
> 
> Did you know you can also use `ORDER BY` in a window function without a `PARTITION BY`? That would rank every employee in the entire company from top to bottom.
> 
> Would you like to see how to use `LEAD()` or `LAG()` to compare an employee's salary directly against the person ranked right above them?

> [!question]- Do all the window functions need this `ORDER BY` to work ?
> 
> Actually, no! Not all window functions **need** `ORDER BY` to function, but its presence (or absence) completely changes the logic of how the calculation is performed.
> 
> We can generally split window functions into two categories based on how they treat ordering:
> 
> ---
> 
> ### 1. Functions that REQUIRE `ORDER BY`
> 
> These functions are based on **position** or **ranking**. Without a specific order, they have no logic to follow. If you omit it, PostgreSQL will either throw an error or give you a useless result (like everyone being Rank 1).
> 
> - **Ranking:** `RANK()`, `DENSE_RANK()`, `ROW_NUMBER()`, `NTILE()`.
>     
> - **Navigation (Positional):** `LEAD()`, `LAG()`, `FIRST_VALUE()`, `LAST_VALUE()`, `NTH_VALUE()`.
>     
>     > _Note: While some systems let you run these without ordering, the results are essentially random because the "next" or "previous" row is undefined._
>     
> 
> ---
> 
> ### 2. Functions where `ORDER BY` is OPTIONAL
> 
> Aggregate functions like `SUM()`, `AVG()`, `MIN()`, and `MAX()` work perfectly fine without an `ORDER BY`. However, adding one changes them into **Running Totals** (Cumulative sums).
> 
> |**Clause**|**Effect on SUM(salary)**|**Result**|
> |---|---|---|
> |**`OVER (PARTITION BY depname)`**|Total department spend.|Every row in 'Sales' shows the same total.|
> |**`OVER (PARTITION BY depname ORDER BY salary)`**|**Running Total** within dept.|Each row adds the current salary to the previous ones.|
> 
> ---
> 
> ### The Secret "Default" Frame
> 
> The reason `ORDER BY` changes `SUM` and `AVG` so drastically is because of a hidden SQL concept called the **Window Frame**.
> 
> - **Without `ORDER BY`**: The default frame is "The entire partition" (all rows).
>     
> - **With `ORDER BY`**: The default frame becomes "From the start of the partition **up to the current row**."
>     
> 
> This is why your `AVG()` in the previous example gave you the department average for every row—it saw the "whole room" at once because there was no ordering to create a sequence.
> 
> ---
> 
> ### Summary Table
> 
> |**Function Type**|**ORDER BY Necessary?**|**Why?**|
> |---|---|---|
> |**Ranking**|**Yes**|You can't have a "top" or "bottom" without a sort order.|
> |**Positional**|**Yes**|You can't find "next" or "previous" in a random pile of rows.|
> |**Aggregates**|**No**|Without it, you get a grand total; with it, you get a running total.|
> 
> Would you like to try writing a **Running Total** query to see how the numbers accumulate as you add each employee's salary?

#### 3. Running total salary per department (ordered by empno)

```bash
psql -c "
SELECT 
    depname,
    empno,
    salary,
    SUM(salary) OVER (PARTITION BY depname ORDER BY empno) AS running_total
FROM empsalary;
"
```

#### 4. Compare current salary to previous salary (using LAG)

```bash
psql -c "
SELECT 
    depname,
    empno,
    salary,
    salary - LAG(salary) OVER (PARTITION BY depname ORDER BY salary) AS diff_from_prev
FROM empsalary;
"
```

#### 5. Top 2 earners per department (using row_number)

```bash
psql -c "
SELECT *
FROM (
    SELECT 
        depname,
        empno,
        salary,
        ROW_NUMBER() OVER (PARTITION BY depname ORDER BY salary DESC) AS rn
    FROM empsalary
) t
WHERE rn <= 2;
"
```


### Quick Mental Model

Think of it this way:

1. The query first does FROM → WHERE → GROUP BY → HAVING (normal processing)
2. Then window functions are calculated **after** grouping but **before** ORDER BY / LIMIT
3. Each row gets to "look back" (and sometimes forward) at other rows in its window

Window functions are one of the biggest "superpowers" in modern SQL — especially in PostgreSQL, which has excellent support for them.

Which pattern are you trying to solve right now (running total, ranking, previous/next value, deduplication, top-N, etc.)?  
I can give you the exact query pattern for your use-case. 😄


# Indexing ![[Indexing.mp4]]

## What Is Indexing in SQL (PostgreSQL)?

**Indexing** is a database optimization technique that allows PostgreSQL to **find rows faster** without scanning the entire table.

> An index is a **separate data structure** that stores column values in a way that makes lookups efficient.

Think of it as a **book index**:

- Without an index → you read every page
    
- With an index → you jump directly to the page
    

---

## Why Indexing Is Needed

Without an index:

```sql
SELECT *
FROM orders
WHERE customer_id = 123;
```

PostgreSQL must do a **sequential scan** (check every row).

With an index:

- PostgreSQL uses the index to locate row pointers
    
- Fetches only matching rows
    
- Drastically reduces I/O
    

---

## How PostgreSQL Indexes Work (Conceptually)

1. Index stores:
    
    - Indexed column values
        
    - Pointers (TIDs) to table rows
        
2. Query planner decides:
    
    - Index scan vs sequential scan
        
3. Index lookup is **O(log n)** instead of **O(n)**
    


> [!question]- You mean it is `O(n)` because as in the above case when searching for a particular `customer_id = 123` the `customer_id` (or any other column) might not be ordered/stored sequentially so indexing creates a sequence( which is ordered) and each index has a pointer to a row or a column to make the access faster or it sorts the `customer_id` also and stores it along with the indexes ?
> 
> Ooo good question — this is the moment where people go from _“I use indexes”_ → _“I actually understand databases”_ 😏
> 
> You’re **very close**, just need to straighten one concept.
> 
> ---
> 
> ## 🔹 Why is it **O(n)** without an index?
> 
> You said:
> 
> > because customer_id might not be ordered
> 
> **YES. Exactly.**  
> PostgreSQL tables (heap tables) are basically:
> 
> > 🧺 A pile of rows in insertion order — **not sorted**
> 
> So when you run:
> 
> ```sql
> SELECT * FROM orders WHERE customer_id = 123;
> ```
> 
> Postgres does:
> 
> ```
> Row 1 → not 123  
> Row 2 → not 123  
> Row 3 → not 123  
> ...
> Row 8,542,991 → FOUND
> ```
> 
> This is called a **Sequential Scan**.
> 
> Time complexity = **O(n)**  
> Because in worst case it checks **every row**.
> 
> ---
> 
> ## 🔹 What the Index Actually Is
> 
> You asked:
> 
> > does indexing create a sequence (ordered) and store pointers?
> 
> 💯 **YES. That’s exactly it.**
> 
> PostgreSQL’s default index type is **B-Tree**.
> 
> An index is a **separate structure** that contains:
> 
> |Indexed Value|Pointer (TID)|
> |---|---|
> |101|→ Row location|
> |102|→ Row location|
> |103|→ Row location|
> |123|→ Row location|
> 
> But here’s the key:
> 
> > ⚠️ The **table is NOT sorted**  
> > ✅ The **index IS sorted**
> 
> ---
> 
> ## 🔹 So What Happens Internally?
> 
> ### Step 1 — You create index
> 
> ```sql
> CREATE INDEX idx_customer ON orders(customer_id);
> ```
> 
> Postgres builds a B-tree like this:
> 
> ```
>                 [500]
>               /       \
>          [200]         [800]
>         /     \       /     \
>    [50] [120] [300] [650] [900]
> ```
> 
> Each leaf node contains:
> 
> ```
> customer_id value → TID (tuple ID = physical row location)
> ```
> 
> ---
> 
> ### Step 2 — Query runs
> 
> ```sql
> SELECT * FROM orders WHERE customer_id = 123;
> ```
> 
> Now Postgres does:
> 
> 1. Binary-style tree search in index → **O(log n)**
>     
> 2. Finds leaf entry for 123
>     
> 3. Reads TID pointer → e.g. (page 845, row 3)
>     
> 4. Jumps directly to that row in table
>     
> 
> So instead of scanning **10 million rows**, it does:
> 
> ```
> log₂(10,000,000) ≈ 24 steps
> ```
> 
> THAT is the performance magic.
> 
> ---
> 
> ## 🔹 Does Index "sort the column"?
> 
> This is where many get confused.
> 
> |Thing|Sorted?|
> |---|---|
> |Table rows|❌ NO|
> |Index entries|✅ YES|
> 
> The index stores:
> 
> ```
> (customer_id value, row pointer)
> ```
> 
> in **sorted order**, but it does **not rearrange the table**.
> 
> ---
> 
> ## 🔹 Why Not Just Sort the Table Then?
> 
> Because:
> 
> - Inserts would be slow (have to reshuffle rows)
>     
> - Multiple indexes need different sort orders
>     
> - Tables are optimized for storage, not search
>     
> 
> So Postgres keeps:
> 
> > 🧺 Heap table (unsorted)  
> > 📘 Index (sorted lookup structure)
> 
> ---
> 
> ## 🔹 Your Understanding — Corrected Version
> 
> Your idea:
> 
> > "indexing creates a sequence (ordered) and each index has a pointer to a row"
> 
> ✔ **Correct**
> 
> Just refine it to:
> 
> > PostgreSQL keeps table rows unsorted, but builds a separate **sorted B-tree structure** containing column values and row pointers (TIDs), allowing fast O(log n) lookup instead of O(n) full scan.
> 
> ---
> 
> ## 🔥 One More Important Insight
> 
> Index lookup is not always used because:
> 
> - If most rows match → sequential scan is faster
>     
> - Planner estimates cost
>     
> 
> So indexes are about **reducing I/O**, not just math.
> 
> ---
> 
> If you want, next I can show:
> 
> 👉 **What happens during INSERT/UPDATE with indexes**  
> 👉 Why too many indexes slow down writes  
> 👉 How composite indexes work
> 
> You’re now officially past beginner DB level 🚀


> [!question]- Pointers (TIDs) to table rows -- What is TIDs ?
> 
> In the world of PostgreSQL, a **TID** stands for **Tuple Identifier**.
> 
> If you think of a database table like a massive physical book, the **TID** is the exact "Page Number" and "Line Number" where a specific piece of data (a tuple/row) is sitting.
> 
> ---
> 
> ### 1. The Anatomy of a TID
> 
> A TID is a 6-byte value represented as a pair of numbers: **`(Block Number, Tuple Index)`**.
> 
> - **Block Number (Page):** PostgreSQL stores data in "pages" (usually 8KB chunks). This tells the system which page to look at.
>     
> - **Tuple Index (Offset):** This tells the system which specific row on that page to grab.
>     
> 
> ### 2. Why does PostgreSQL use them?
> 
> TIDs are the "low-level" addresses used by the system to find data instantly without scanning the whole table.
> 
> - **Indexes:** When you create an index on a column (like `email`), the index doesn't actually store the whole row. It stores the email address and the **TID**. Once it finds the email in the index, it uses the TID to "jump" straight to the data on the disk.
>     
> - **MVCC (Versioning):** Because PostgreSQL uses Multi-Version Concurrency Control, when you `UPDATE` a row, Postgres doesn't actually overwrite the old data. It creates a **new row** at a **new TID** and marks the old one as "dead."
>     
> 
> ---
> 
> ### 3. How to see TIDs in action
> 
> You can actually see the hidden TID of any row in your Debian terminal by querying the "hidden" `ctid` column:
> 
> SQL
> 
> ```
> SELECT ctid, * FROM empsalary;
> ```
> 
> **The result will look like this:**
> 
> | ctid | depname | empno | salary |
> 
> | :--- | :--- | :--- | :--- |
> 
> | **(0,1)** | sales | 1 | 5000 |
> 
> | **(0,2)** | sales | 2 | 4800 |
> 
> | **(1,1)** | IT | 3 | 6000 |
> 
> > [!IMPORTANT]
> > 
> > **Warning:** Never use a TID as a permanent reference (like a Primary Key) in your application code. TIDs change whenever a table is `VACUUM FULL`ed or sometimes when a row is updated. They are for the database's internal use, not for your business logic!
> 
> ---
> 
> ### The "Table Bloat" Connection
> 
> Since you're working on a Debian system, you might eventually run into "Bloat." This happens when many TIDs point to "dead" versions of rows that haven't been cleaned up yet.
> 
> **Would you like me to show you how to check if your table has too many "dead" TIDs (bloat) using the `pg_stat_user_tables` view?**


---

## Default Index Type: B-Tree (Most Important)

```sql
CREATE INDEX idx_orders_customer
ON orders(customer_id);
```

### B-Tree supports:

- `=`
    
- `<`, `>`, `<=`, `>=`
    
- `BETWEEN`
    
- `IN`
    
- `ORDER BY`
    
- `LIKE 'abc%'`
    

This covers ~90% of use cases.

---

## Other Index Types (PostgreSQL-Specific Strength)

### 1. Hash Index

```sql
CREATE INDEX idx_hash ON users USING HASH(email);
```

- Equality only
    
- Rarely used
    

---

### 2. GIN (Generalized Inverted Index)

Best for **multi-valued data**.

```sql
CREATE INDEX idx_tags ON posts USING GIN(tags);
```

Use cases:

- Arrays
    
- JSONB
    
- Full-text search
    

---

### 3. GiST (Generalized Search Tree)

Used for **geometric / proximity searches**.

```sql
CREATE INDEX idx_location ON places USING GiST(location);
```

---

### 4. BRIN (Block Range Index)

For **huge, naturally ordered tables**.

```sql
CREATE INDEX idx_logs_time ON logs USING BRIN(created_at);
```

Very small, very fast for time-series data.

---

## Unique Index

Enforces uniqueness **and** speeds up lookup.

```sql
CREATE UNIQUE INDEX idx_users_email
ON users(email);
```

Equivalent to:

```sql
UNIQUE (email)
```

---

## Composite (Multi-Column) Index

```sql
CREATE INDEX idx_orders_customer_date
ON orders(customer_id, order_date);
```

### Column order matters:

- `(customer_id)` → usable
    
- `(customer_id, order_date)` → usable
    
- `(order_date)` → NOT usable alone
    

---

## Partial Index (Very Powerful)

Index only a subset of rows.

```sql
CREATE INDEX idx_active_orders
ON orders(customer_id)
WHERE status = 'active';
```

Faster and smaller than full index.

---

## Expression Index

Index on computed values.

```sql
CREATE INDEX idx_lower_email
ON users(LOWER(email));
```

Query must match expression exactly.

---

## When Indexes Hurt Performance

Indexes slow down:

- `INSERT`
    
- `UPDATE`
    
- `DELETE`
    

Because indexes must be maintained.

> More indexes ≠ better performance.

---

## How PostgreSQL Chooses an Index

Use:

```sql
EXPLAIN ANALYZE
SELECT *
FROM orders
WHERE customer_id = 123;
```

Look for:

- `Index Scan`
    
- `Bitmap Index Scan`
    

---

## Common Indexing Mistakes

1. Indexing low-cardinality columns (e.g., `gender`)
    
2. Too many indexes
    
3. Wrong column order in composite indexes
    
4. Indexing columns never used in `WHERE` or `JOIN`
    

---

## Practical Rules of Thumb

- Index columns used in:
    
    - `WHERE`
        
    - `JOIN`
        
    - `ORDER BY`
        
    - `GROUP BY`
        
- Use composite indexes carefully
    
- Use partial indexes for filtered queries
    
- Measure with `EXPLAIN ANALYZE`
    

---

## Summary

- Indexing improves read performance
    
- PostgreSQL uses multiple index types
    
- B-Tree is the default and most common
    
- Indexes trade write speed for read speed
    
- Correct indexing is **one of the most valuable SQL skills**
    

---

If you want, I can:

- Analyze a slow query
    
- Design indexes for a real schema
    
- Explain why an index is not used
    
- Compare PostgreSQL indexing with MySQL
    

---

# Common Table Expressions (CTEs) — Using `empsalary` and `departments`

## Tables Used

> [!Multi-Column]
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |

---

## What Is a CTE?

A **Common Table Expression (CTE)** is a **named, temporary result set** defined using `WITH`, available **only to the query that follows**.

CTEs allow you to:

- Decompose complex queries into steps
    
- Improve readability
    
- Express logic declaratively
    
- Write recursive queries
    

---

## Basic Syntax

```sql
WITH cte_name AS (
    SELECT ...
)
SELECT ...
FROM cte_name;
```

---

## Simple Example — High Salary Employees

> “List employees earning more than 6,000.”

```sql
WITH high_salary AS (
    SELECT empno, depname, salary
    FROM empsalary
    WHERE salary > 6000
)
SELECT *
FROM high_salary;
```

### Execution Model (Conceptual)

1. PostgreSQL evaluates `high_salary`
    
2. The result is named
    
3. The outer query consumes it
    

---

## Why Use a CTE?

### 1. Readability (Primary Reason)

#### Without a CTE (nested logic)

```sql
SELECT *
FROM empsalary
WHERE depname IN (
    SELECT depname
    FROM empsalary
    GROUP BY depname
    HAVING AVG(salary) > 6000
);
```

#### With a CTE (clear intent)

```sql
WITH high_paying_departments AS (
    SELECT depname
    FROM empsalary
    GROUP BY depname
    HAVING AVG(salary) > 6000
)
SELECT *
FROM empsalary
WHERE depname IN (
    SELECT depname FROM high_paying_departments
);
```

This reads like:

> “First find high-paying departments, then list their employees.”

---

## Logical Decomposition with Multiple CTEs

> “Show the **top 2 highest-paid employees per department**, including department details.”

```sql
WITH ranked_employees AS (
    SELECT
        empno,
        depname,
        salary,
        RANK() OVER (PARTITION BY depname ORDER BY salary DESC) AS rnk
    FROM empsalary
),
top_earners AS (
    SELECT *
    FROM ranked_employees
    WHERE rnk <= 2
)
SELECT
    t.empno,
    t.salary,
    d.dept_name,
    d.manager,
    d.location
FROM top_earners t
JOIN departments d
  ON t.depname = d.dept_code;
```

Each CTE performs **one logical step**:

1. Rank employees
    
2. Filter top earners
    
3. Join metadata
    

---

## Multiple CTEs in One Query

```sql
WITH dept_avg AS (
    SELECT depname, AVG(salary) AS avg_salary
    FROM empsalary
    GROUP BY depname
),
above_avg_employees AS (
    SELECT e.*
    FROM empsalary e
    JOIN dept_avg d
      ON e.depname = d.depname
     AND e.salary > d.avg_salary
)
SELECT *
FROM above_avg_employees;
```

CTEs execute **top-down** conceptually and can depend on prior CTEs.

---

## Recursive CTE — Salary Bands per Department

While your tables are not hierarchical, recursive CTEs can still model **derived hierarchies**.

> “Create salary bands of 1,000 per department.”

```sql
WITH RECURSIVE salary_bands AS (
    SELECT
        depname,
        0 AS band_start,
        1000 AS band_end
    FROM empsalary
    GROUP BY depname

    UNION ALL

    SELECT
        depname,
        band_start + 1000,
        band_end + 1000
    FROM salary_bands
    WHERE band_end < 9000
)
SELECT *
FROM salary_bands
ORDER BY depname, band_start;
```

### Key Recursive Rules

- **Anchor query** defines the base rows
    
- **Recursive query** references the CTE itself
    
- **Termination condition is mandatory**


> [!question]- What is UNION ALL ?
> 
> In PostgreSQL, **`UNION ALL`** is an operator used to combine the result sets of two or more queries into a single result set.
> 
> Think of it like **stacking LEGO bricks**: the first query creates the bottom layer, and the second query places its results directly on top of them.
> 
> ---
> 
> ### 1. How it works in your RECURSIVE CTE
> 
> In a `WITH RECURSIVE` query, `UNION ALL` acts as the "glue" between two distinct parts:
> 
> - **The Anchor Member (The Top Query):** This runs once to create the starting point (e.g., your initial salary bands of 0 to 1000).
>     
> - **The Recursive Member (The Bottom Query):** This runs repeatedly, taking the results of the previous step and adding to them (e.g., adding 1000 to the bands until it hits 9000).
>     
> 
> The `UNION ALL` simply keeps appending these new "rows" to the final table until the recursion finishes.
> 
> ---
> 
> ### 2. `UNION` vs. `UNION ALL`
> 
> This is the most common point of confusion. The difference is all about how they handle **duplicates**:
> 
> |**Operator**|**Behavior**|**Performance**|
> |---|---|---|
> |**`UNION`**|Combines rows and **removes duplicates**.|**Slower** (Postgres has to sort and "de-duplicate" the data).|
> |**`UNION ALL`**|Combines rows and **keeps everything**, even duplicates.|**Faster** (Postgres just appends the data without checking it).|
> 
> > [!TIP]
> > 
> > **Rule of Thumb:** Always use `UNION ALL` unless you specifically need to hide duplicate rows. It is significantly lighter on your Debian server's CPU and memory.
> 
> ---
> 
> ### 3. The Strict Rules for `UNION ALL`
> 
> For `UNION ALL` to work, the queries must follow these "matching" rules:
> 
> 1. **Same Number of Columns:** If Query A has 3 columns, Query B must have 3 columns.
>     
> 2. **Compatible Data Types:** You cannot union a column of `TEXT` with a column of `INTEGER`.
>     
> 3. **Order of Columns:** The columns must be in the same order (e.g., `depname` then `salary`).
>     
> 
> ---
> 
> ### Visualization of your Query
> 
> Since your query uses `RECURSIVE`, the `UNION ALL` is building a "stack" that looks like this:
> 
> 4. **Step 1 (Anchor):** `Sales | 0 | 1000`
>     
> 5. **Step 2 (Recursion 1):** `Sales | 1000 | 2000` (Added via UNION ALL)
>     
> 6. **Step 3 (Recursion 2):** `Sales | 2000 | 3000` (Added via UNION ALL)
>     
> 7. _...and so on._
>     
> 
> ### Ready to see it in action?
> 
> If you run that query in your terminal, you'll see a long list of bands. **Would you like me to show you how to JOIN this recursive table back to your `empsalary` table to see how many employees fall into each $1000 band?**

---

## CTE vs Subquery vs View (Applied to Your Tables)

|Feature|CTE|Subquery|View|
|---|---|---|---|
|Readability|Excellent|Poor–Fair|Excellent|
|Scope|Single query|Inline|Persistent|
|Reusable|Within query|No|Yes|
|Recursive|Yes|No|No|
|Use case|Analytics, logic|Simple filters|Reporting|

---

## PostgreSQL-Specific Behavior (Critical)

### Before PostgreSQL 12

- CTEs were **always materialized**
    
- Could degrade performance
    

### PostgreSQL 12+

- CTEs are **inlined by default**
    
- Optimizer can push predicates and reorder joins
    

You can control behavior explicitly:

```sql
WITH dept_avg AS MATERIALIZED (
    SELECT depname, AVG(salary)
    FROM empsalary
    GROUP BY depname
)
SELECT * FROM dept_avg;
```

or

```sql
WITH dept_avg AS NOT MATERIALIZED (
    SELECT depname, AVG(salary)
    FROM empsalary
    GROUP BY depname
)
SELECT * FROM dept_avg;
```


> [!question]- What is the meaning of a materialized CTE ? What do you mean when you say View is not recursive while CTE is ?
> 
> Your write-up is already solid. I will answer **only the two questions you asked**, precisely and at the right conceptual depth.
> 
> ---
> 
> ## 1. What does **“materialized CTE”** actually mean?
> 
> ### Short definition
> 
> A **materialized CTE** is a CTE whose result is **fully computed and stored in a temporary work table** _before_ the outer query runs, and **cannot be re-optimized or partially evaluated** by the planner.
> 
> Think of it as:
> 
> > “Run this subquery once, store its full result, then treat it like a static table.”
> 
> ---
> 
> ### Execution difference (critical)
> 
> Consider:
> 
> ```sql
> WITH dept_avg AS MATERIALIZED (
>     SELECT depname, AVG(salary) AS avg_salary
>     FROM empsalary
>     GROUP BY depname
> )
> SELECT *
> FROM dept_avg
> WHERE avg_salary > 6000;
> ```
> 
> **What happens internally:**
> 
> 1. PostgreSQL executes `dept_avg`
>     
> 2. Computes _all department averages_
>     
> 3. Stores them in a temporary structure
>     
> 4. Only _after that_ applies `WHERE avg_salary > 6000`
>     
> 
> The optimizer **cannot**:
> 
> - Push the `WHERE` clause into the CTE
>     
> - Reorder joins
>     
> - Avoid computing unused rows
>     
> 
> ---
> 
> ### NOT MATERIALIZED (PostgreSQL 12+ default)
> 
> ```sql
> WITH dept_avg AS NOT MATERIALIZED (
>     SELECT depname, AVG(salary) AS avg_salary
>     FROM empsalary
>     GROUP BY depname
> )
> SELECT *
> FROM dept_avg
> WHERE avg_salary > 6000;
> ```
> 
> Now PostgreSQL may:
> 
> - Inline the CTE into the outer query
>     
> - Push filters _into_ the aggregation
>     
> - Reorder execution
>     
> - Avoid computing unnecessary rows
>     
> 
> Conceptually this behaves like a **named subquery**.
> 
> ---
> 
> ### Why MATERIALIZED exists at all
> 
> Materialization is **sometimes necessary** and **sometimes beneficial**:
> 
> #### You _want_ MATERIALIZED when:
> 
> - The CTE is referenced **multiple times**
>     
> - The computation is **expensive**
>     
> - You need **stable semantics** (same result reused)
>     
> - You rely on **side-effect-free determinism**
>     
> 
> Example:
> 
> ```sql
> WITH expensive_calc AS MATERIALIZED (
>     SELECT ..., heavy_function(...)
>     FROM big_table
> )
> SELECT a.*, b.*
> FROM expensive_calc a
> JOIN expensive_calc b ON ...
> ```
> 
> Without materialization, the function might execute twice.
> 
> ---
> 
> ### Mental model
> 
> |CTE mode|Acts like|
> |---|---|
> |MATERIALIZED|Temporary table|
> |NOT MATERIALIZED|Inline view / subquery|
> 
> ---
> 
> ## 2. Why is a **View not recursive**, but a **CTE can be recursive**?
> 
> This is a **foundational SQL design constraint**, not an implementation detail.
> 
> ---
> 
> ### What recursion means in SQL
> 
> Recursion requires:
> 
> 1. A result set
>     
> 2. That result set referencing **itself**
>     
> 3. Iterative expansion until a termination condition
>     
> 
> This is exactly what `WITH RECURSIVE` provides.
> 
> ---
> 
> ### Why a **CTE can be recursive**
> 
> A recursive CTE is defined **inside a single query execution context**:
> 
> ```sql
> WITH RECURSIVE t(n) AS (
>     SELECT 1           -- anchor
>     UNION ALL
>     SELECT n + 1       -- recursive step
>     FROM t
>     WHERE n < 5
> )
> SELECT * FROM t;
> ```
> 
> Key properties:
> 
> - `t` exists only during query execution
>     
> - PostgreSQL controls iteration
>     
> - The engine knows when to stop
>     
> - There is no global dependency cycle
>     
> 
> This is safe and well-defined.
> 
> ---
> 
> ### Why a **View cannot be recursive**
> 
> A view is:
> 
> ```sql
> CREATE VIEW v AS
> SELECT ...
> ```
> 
> A view is a **persistent schema object**.
> 
> If recursion were allowed:
> 
> ```sql
> CREATE VIEW v AS
> SELECT * FROM v;
> ```
> 
> This would mean:
> 
> - The view definition depends on itself
>     
> - There is no execution boundary
>     
> - No termination semantics
>     
> - Infinite expansion at planning time
>     
> 
> This breaks:
> 
> - Query planning
>     
> - Dependency resolution
>     
> - Schema validation
>     
> - Optimization guarantees
>     
> 
> Hence **SQL forbids self-referencing views**.
> 
> ---
> 
> ### Even indirect recursion is forbidden in views
> 
> ```sql
> CREATE VIEW v1 AS SELECT * FROM v2;
> CREATE VIEW v2 AS SELECT * FROM v1;
> ```
> 
> PostgreSQL rejects this.
> 
> Why?  
> Because views are **static definitions**, not execution-time constructs.
> 
> ---
> 
> ### Core distinction (this is the key insight)
> 
> |Aspect|CTE|View|
> |---|---|---|
> |Lifetime|Single query|Persistent object|
> |Execution control|Query planner|Schema level|
> |Self-reference|Allowed (recursive)|Forbidden|
> |Iteration semantics|Explicit (`UNION ALL`)|None|
> |Termination rule|Mandatory|Impossible|
> 
> ---
> 
> ### One-line intuition
> 
> > **A recursive CTE is an algorithm.  
> > A view is a definition.  
> > Definitions cannot depend on themselves.**
> 
> ---
> 
> ## Final takeaway
> 
> - **Materialized CTE** = computed once, stored, optimization barrier
>     
> - **NOT MATERIALIZED CTE** = inlined, optimizer-friendly
>     
> - **CTEs can be recursive** because they execute _within_ a query
>     
> - **Views cannot be recursive** because they are _schema-level definitions_
>     
> 
> If you want, next we can:
> 
> - Walk through `EXPLAIN ANALYZE` showing materialization in action, or
>     
> - Compare recursive CTEs vs procedural loops (PL/pgSQL), or
>     
> - Analyze when materialization _hurts_ performance in analytic queries
>     
> 
> Just say which direction you want to go.

---

## When to Use CTEs (With Your Schema)

### Use CTEs when:

- Computing department aggregates
    
- Ranking employees
    
- Mixing payroll with department metadata
    
- Writing multi-step analytical queries
    
- Needing recursion or window functions
    

### Avoid CTEs when:

- A single `JOIN` suffices
    
- Performance is critical on PostgreSQL < 12
    
- Logic is trivial
    

---

## Execution Order (Conceptual)

1. CTE definitions
    
2. Main SELECT
    
3. Final result
    

> Note: The planner may reorder execution internally.

---

## Common Pitfalls

1. Assuming CTEs persist beyond the query
    
2. Overusing CTEs for trivial joins
    
3. Forgetting termination in recursive CTEs
    
4. Ignoring materialization cost on older PostgreSQL
    

---

## Summary

- CTEs are named, temporary result sets
    
- Defined with `WITH`
    
- Excellent for payroll and HR analytics
    
- Support recursion and window functions
    
- PostgreSQL 12+ optimizes them aggressively
    

---

If you want next, I can:

- Rewrite **correlated subqueries** on `empsalary` using CTEs
    
- Show **EXPLAIN ANALYZE** comparisons (CTE vs subquery)
    
- Build **departmental payroll reports** step by step
    
- Demonstrate **CTE vs window-function-only solutions**
    

Just specify the direction.


> [!question]- You mean CTE is basically a readable subquery ?
> 
> Spot on. If a subquery is a "side note" crammed into the middle of a sentence, a CTE is a **clearly labeled definition** at the top of the page.
> 
> While they often achieve the same result, here is why calling it a "readable subquery" is the perfect way to think about it, along with the one big exception where they do much more.
> 
> ---
> 
> ## 1. The "Clean Code" Factor
> 
> Subqueries tend to grow from the **inside out**, making them hard to follow. CTEs grow **top to bottom**, which matches how humans read.
> 
> **The Subquery Way (Messy):**
> 
> SQL
> 
> ```sql
> SELECT employee_name 
> FROM (SELECT * FROM employees WHERE department = 'Sales') AS sales_team
> WHERE salary > (SELECT AVG(salary) FROM employees);
> ```
> 
> **The CTE Way (Readable):**
> 
> SQL
> 
> ```sql
> WITH sales_team AS (
>     SELECT * FROM employees WHERE department = 'Sales'
> ),
> average_salary AS (
>     SELECT AVG(salary) AS value FROM employees
> )
> SELECT employee_name 
> FROM sales_team, average_salary
> WHERE salary > average_salary.value;
> ```
> 
> ---
> 
> ## 2. The "Reuse" Factor
> 
> In a standard subquery, if you need the same logic twice (e.g., joining a filtered list of users to both an `orders` table and a `returns` table), you have to copy-paste the entire subquery.
> 
> With a CTE, you **define it once** and reference it as many times as you want in the main query. It behaves like a temporary view that only exists for those few milliseconds the query is running.
> 
> ---
> 
> ## 3. The One "Superpower": Recursion
> 
> This is where the "it's just a subquery" comparison breaks down. A standard subquery **cannot reference itself**.
> 
> A **Recursive CTE** can. This is essential for data that has a "parent-child" relationship, like a comment thread with nested replies or a corporate hierarchy.
> 
> ---
> 
> ## Summary of the "Vibe"
> 
> - **Subqueries** are great for quick, one-off logic (e.g., `WHERE id IN (SELECT id...)`).
>     
> - **CTEs** are for "storytelling"—breaking a complex data transformation into logical, named steps.
>     
> 
> **Would you like to try refactoring a messy subquery you're currently working on into a clean CTE? Paste it here and I'll do the heavy lifting!**


# Temporary table

While a CTE is like a temporary "variable" that exists only for a single query, a **Temporary Table** is like a **scratchpad** that stays open for your entire database session.

> [!question]- While a CTE is like a temporary "variable" that exists only for a single query -- You mean it exists till a ; is encountered or in a single query console of psql.
> 
> Exactly. It exists until the **semicolon (`;`)** is encountered.
> 
> Once that single statement finishes executing, the CTE is wiped from the database's short-term memory. It doesn't matter if you are in the same psql console window; the next time you hit enter, that CTE name is gone.
> 
> Here is the breakdown of "existence" across the three concepts we've discussed:
> 
> ### 1. The CTE (The "Flash")
> 
> - **Boundary:** The semicolon `;`.
>     
> - **Memory:** It lives in the execution plan.
>     
> - **Analogy:** A "Let" or "Const" variable inside a single function. Once the function returns, the variable is destroyed.
>     
> 
> ### 2. The Temp Table (The "Session")
> 
> - **Boundary:** Your connection/window is closed.
>     
> - **Memory:** Stored in a temporary area on disk/memory.
>     
> - **Analogy:** A global variable in a script. As long as the script is running, the variable is there. Once the script finishes (you close psql), it's gone.
>     
> 
> ---
> 
> ### A Visual Comparison of Scope
> 
> |**Scenario**|**Can I use it in the next query?**|**Example**|
> |---|---|---|
> |**CTE**|**No.**|`WITH x AS (...) SELECT * FROM x;`<br><br>  <br><br>(Next line `SELECT * FROM x;` fails)|
> |**Temp Table**|**Yes.**|`CREATE TEMP TABLE x...;`<br><br>  <br><br>(Next line `SELECT * FROM x;` works)|
> |**Permanent Table**|**Yes.**|`CREATE TABLE x...;`<br><br>  <br><br>(Works until someone runs `DROP TABLE`)|
> 
> ---
> 
> ### One tiny "Psql Console" catch
> 
> If you are using a GUI tool (like pgAdmin or DBeaver) and you highlight **only** the `SELECT` part of a `WITH` block, the query will fail because the tool doesn't send the `WITH` definition to the server. You have to highlight the entire block—from `WITH` to `;`—for it to work.
> 
> **Do you want to see what happens when you try to join two different CTEs together in a single statement?**

In PostgreSQL, a temporary table is a special type of table that is automatically dropped (deleted) when your current session or connection ends.

---

## Key Characteristics

- **Isolation:** Temp tables are private. If you create a table named `temp_users`, only you can see it. Another user connected to the same database cannot see your temp table, even if they use the exact same name.
    
- **Lifespan:** By default, it lives until you close your psql prompt or disconnect your application from the database.
    
- **Performance:** They are stored in a special schema and are often faster for complex manipulations because they don't require the same level of logging as permanent tables.
    

---

## When to use a Temp Table (vs. a CTE)

Since you now know CTEs are "readable subqueries," here is when you should upgrade to a Temp Table:

1. **Multiple Passes:** If you need to run 5 different queries against the same subset of data, a CTE would re-run its logic every time. A Temp Table saves the result so you only calculate it once.
    
2. **Indexing:** You **cannot** index a CTE. You **can** index a Temp Table. If you are dealing with millions of rows in your temporary set, an index is a lifesaver.
    
3. **Complex Logic:** If you need to perform "Step A," then "Step B," then "Step C" (perhaps using Procedural SQL or a script), a Temp Table holds the state between those steps.
    

---

## Syntax in PostgreSQL

Creating one is almost identical to a regular table, just add the `TEMP` keyword:


```SQL
-- 1. Create the table
CREATE TEMP TABLE active_customers AS
SELECT id, name, email 
FROM customers 
WHERE last_login > '2023-01-01';

-- 2. Use it like a normal table (even add an index!)
CREATE INDEX idx_temp_id ON active_customers(id);

SELECT * FROM active_customers WHERE name LIKE 'A%';

-- 3. It disappears when you disconnect, or you can drop it manually
DROP TABLE active_customers;
```

---

## Comparison Summary

|**Feature**|**CTE**|**Temporary Table**|
|---|---|---|
|**Storage**|Memory (mostly)|Disk/Memory|
|**Can use Indexes?**|No|**Yes**|
|**Duration**|One query|One session (connection)|
|**Best for...**|Readability/Recursion|Intermediate storage/Large data|

**Would you like to see how to use a Temporary Table within a PostgreSQL Function or Stored Procedure?**


# Joins

**Joins** in SQL (PostgreSQL) are used to combine rows from **two or more tables** based on a related column between them — usually a foreign key relationship.

Since you already have the `empsalary` table, we'll create one more small table called `departments` so we can demonstrate realistic join examples.

## Step 1: Create a second table (departments)(already created at the top)

Run this once (you can add it to your previous script):

```sql
DROP TABLE IF EXISTS departments;

CREATE TABLE departments (
    dept_code   TEXT PRIMARY KEY,          -- e.g. 'sales', 'IT'
    dept_name   TEXT NOT NULL,
    manager     TEXT,
    location    TEXT
);

INSERT INTO departments (dept_code, dept_name, manager, location) VALUES
    ('sales',   'Sales & Marketing',    'Sarah Jain',    'Chennai'),
    ('IT',      'Information Technology','Raj Patel',     'Bangalore'),
    ('support', 'Customer Support',     'Priya Menon',   'Hyderabad'),
    ('hr',      'Human Resources',      'Anil Kumar',    'Mumbai');     -- extra dept with no employees
```

Now you have:

- `empsalary` → employee-level data (depname matches dept_code)
- `departments` → department metadata

## The Most Important JOIN Types (with examples)

| Join Type          | What it returns                                      | Rows from left table | Rows from right table | When to use                                      |
|---------------------|------------------------------------------------------|----------------------|------------------------|--------------------------------------------------|
| **INNER JOIN**      | Only matching rows from both tables                  | Only matching        | Only matching          | Most common – you want data that exists in both  |
| **LEFT JOIN**       | All rows from left + matching from right (NULL if no match) | **All**              | Matching or NULL       | Keep everything from main table                  |
| **RIGHT JOIN**      | All rows from right + matching from left             | Matching or NULL     | **All**                | Less common (usually rewrite as LEFT)            |
| **FULL OUTER JOIN** | All rows from both (NULL where no match)             | **All**              | **All**                | Rare – see gaps in both directions               |
| **CROSS JOIN**      | Cartesian product – every row × every row            | **All**              | **All**                | Rare (usually accidental or for combinations)    |

## Practical Examples (using your tables)

### 1. INNER JOIN (most common)

```bash
psql -c "
SELECT 
    e.empno,
    e.depname,
    e.salary,
    d.dept_name,
    d.manager,
    d.location
FROM empsalary e
INNER JOIN departments d 
    ON e.depname = d.dept_code
ORDER BY e.salary DESC;
"
```

→ Result: only departments that have employees (no 'hr')

### 2. LEFT JOIN (keep all employees, even if department missing)

```bash
psql -c "
SELECT 
    e.empno,
    e.depname           AS code_in_salary,
    e.salary,
    d.dept_name         AS full_dept_name,
    d.manager
FROM empsalary e
LEFT JOIN departments d 
    ON e.depname = d.dept_code
ORDER BY e.salary DESC;
"
```

→ If any `depname` didn't exist in `departments`, you would still see the employee row (with NULL in dept_name, manager, etc.)

### 3. RIGHT JOIN (keep all departments, even without employees)

```bash
psql -c "
SELECT 
    d.dept_code,
    d.dept_name,
    d.manager,
    e.empno,
    e.salary
FROM empsalary e
RIGHT JOIN departments d 
    ON e.depname = d.dept_code
ORDER BY d.dept_code, e.salary DESC NULLS LAST;
"
```

→ You will see 'hr' department with NULL employee info

### 4. FULL OUTER JOIN (see everything – matches + orphans both sides)

```bash
psql -c "
SELECT 
    COALESCE(e.depname, d.dept_code) AS department,
    e.empno,
    e.salary,
    d.dept_name,
    d.manager
FROM empsalary e
FULL OUTER JOIN departments d 
    ON e.depname = d.dept_code
ORDER BY department, salary DESC NULLS LAST;
"
```

### 5. Self Join (same table – example: compare salaries within department)

```bash
psql -c "
SELECT 
    a.empno          AS emp1,
    a.salary         AS salary1,
    b.empno          AS emp2,
    b.salary         AS salary2,
    a.salary - b.salary AS difference
FROM empsalary a
INNER JOIN empsalary b 
    ON a.depname = b.depname 
   AND a.empno < b.empno                -- avoid self & duplicates
WHERE a.depname = 'sales'
ORDER BY difference DESC;
"
```


> [!question]- is FULL OUTER JOIN same as just OUTER JOIN and does it only keeps the unique items from the selected columns on which join is performed so that the joined values no duplicates ?
> 
> **No — `FULL OUTER JOIN` is not exactly the same as just `OUTER JOIN`, and it does *not* automatically keep only unique values or remove duplicates from the join key.**
> 
> Let me explain both parts clearly.
> 
> ### 1. Is `FULL OUTER JOIN` the same as `OUTER JOIN`?
> 
> **Yes — in practice they are the same in PostgreSQL (and in most modern SQL databases).**
> 
> - `FULL OUTER JOIN` = `FULL JOIN`
> - The word `OUTER` is **optional** and usually just makes the intent more explicit.
> 
> These are **identical** in PostgreSQL:
> 
> ```sql
> SELECT * FROM empsalary e
> FULL OUTER JOIN departments d ON e.depname = d.dept_code;
> 
> -- Exactly the same as:
> SELECT * FROM empsalary e
> FULL JOIN departments d ON e.depname = d.dept_code;
> 
> -- Also same as (very rare style):
> SELECT * FROM empsalary e
> OUTER JOIN departments d ON e.depname = d.dept_code;   -- FULL is implied by context, but not recommended
> ```
> 
> **Important notes:**
> 
> - `OUTER` without `FULL` / `LEFT` / `RIGHT` is **not standard** and may not be supported everywhere.
> - You usually write one of: `FULL JOIN`, `FULL OUTER JOIN`, `LEFT JOIN`, `LEFT OUTER JOIN`, `RIGHT JOIN`, `RIGHT OUTER JOIN`.
> - `JOIN` by itself = `INNER JOIN` (no `OUTER` keyword needed).
> 
> So in short:  
> **`FULL OUTER JOIN` ⇔ `FULL JOIN`** → same thing  
> Just use `FULL JOIN` or `FULL OUTER JOIN` — both are correct and very common.
> 
> ### 2. Does `FULL OUTER JOIN` remove duplicates or keep only unique join-key values?
> 
> **No — it does NOT remove duplicates and does NOT deduplicate anything.**
> 
> - `FULL OUTER JOIN` returns **all rows from both tables**, preserving **every row** even if the join key appears multiple times.
> - If the join condition matches **multiple rows** on one side (or both), you get **a Cartesian product for those matching groups** → this creates duplicates in the result.
> 
> #### Example with your tables
> 
> Your `empsalary` has:
> 
> depname | empno | salary  
> ---|---|---
> sales   | 11    | 5200  
> sales   | 1     | 5000  
> sales   | 2     | 4800  
> IT      | 5     | 8000  
> ...  
> 
> Now imagine we add a duplicate department in `departments` (just for demonstration):
> 
> ```run-bash
> psql -c "
> -- Remove the PK constraint 
> ALTER TABLE departments DROP CONSTRAINT departments_pkey;
> 
> INSERT INTO departments (dept_code, dept_name) 
> VALUES ('sales', 'Sales Duplicate');
> 
> -- Now run:
> 
> SELECT 
>     e.depname,
>     e.empno,
>     e.salary,
>     d.dept_name
> FROM empsalary e
> FULL OUTER JOIN departments d 
>     ON e.depname = d.dept_code
> WHERE e.depname = 'sales' OR d.dept_code = 'sales';
> "
> ```
> 
> You will get **3 employees × 2 departments = 6 rows** for sales (instead of 3), because each employee matches **both** department rows.
> 
> **Result snippet (simplified):**
> 
> depname | empno | salary | dept_name  
> ---|---|---|---
> sales   | 11    | 5200   | Sales & Marketing  
> sales   | 11    | 5200   | Sales Duplicate  
> sales   | 1     | 5000   | Sales & Marketing  
> sales   | 1     | 5000   | Sales Duplicate  
> ... (6 rows total for sales)
> 
> → **Duplicates appear** when the join key is **not unique** on one or both sides.
> 
> #### Summary – Duplicate behavior
> 
> | Situation on join key (`depname = dept_code`) | What `FULL OUTER JOIN` does                          | Rows in result                  |
> |------------------------------------------------|-------------------------------------------------------|---------------------------------|
> | Unique on both sides                           | 1:1 match → clean result                              | = number of matches + orphans   |
> | Duplicate(s) on left table                     | Each left row matches every matching right row        | More rows (multiplication)      |
> | Duplicate(s) on right table                    | Same — multiplication                                 | More rows                       |
> | Duplicate on both sides                        | Full Cartesian product for the duplicate groups       | Can become very large           |
> 
> **`FULL OUTER JOIN` never removes duplicates by itself.**  
> If you want to avoid / remove duplicates you must:
> 
> - Use `DISTINCT` (on all columns or selected ones)
> - Aggregate (`GROUP BY`, `COUNT`, `MAX`, etc.)
> - Fix data model (make join keys unique with unique index / primary key)
> - Use `EXISTS` / semi-join instead if you just want presence check
> 
> Quick example to remove duplicate department effect:
> 
> ```sql
> SELECT DISTINCT 
>     e.depname,
>     e.empno,
>     e.salary,
>     d.dept_name
> FROM empsalary e
> FULL OUTER JOIN departments d ON e.depname = d.dept_code;
> ```
> 
> But `DISTINCT` is usually a band-aid — better to have clean data or use the right join type.
> 
> Does this clear up your doubt?  
> If you have a specific query where you're seeing unexpected duplicates, paste it — I can help fix it. 😊

## Quick JOIN Tips for PostgreSQL

- Always use **table aliases** (`e`, `d`, `a`, `b`) — makes code shorter & clearer
- Write `ON` condition **explicitly** (avoid old `WHERE` style joins)
- Column order in `ON` doesn't matter: `a.col = b.col` is same as `b.col = a.col`
- Use `USING (column)` shorthand when column name is identical:

  ```bash
  psql -c "
  FROM empsalary e
  LEFT JOIN departments d USING (dept_code);   -- if you rename depname → dept_code
  "
  ```

- Performance: Indexes on join columns (especially foreign keys) make huge difference

  ```bash
  psql -c "
  CREATE INDEX idx_empsalary_depname ON empsalary (depname);
  "
  ```

Which join style are you trying to use right now?  
Do you want to:

- show department names instead of codes?
- find employees without department?
- compare salaries between people?
- something else?

Just tell me your goal — I’ll give you the exact query. 😄

# Clauses in SQL

When we talk about “SQL clauses”, we usually mean the clauses of a `SELECT` statement, since that’s the most composition-heavy query type.

Below is the **logical structure**, the **execution order caveat**, and a **mnemonic** that actually works.

---

## 1️⃣ Core Clauses in a `SELECT` Statement

Canonical form:

```sql
SELECT column_list
FROM table_source
JOIN other_table ON condition
WHERE row_condition
GROUP BY grouping_columns
HAVING group_condition
ORDER BY sort_columns
LIMIT row_count OFFSET offset_value;
```

Now let’s break them down precisely.

---

### 1. `SELECT`

Specifies which columns or expressions to return.

```sql
SELECT name, salary * 12 AS annual_salary
```

#### ⚠ Caveat:

* Aliases defined here **cannot be used in `WHERE`** (because `WHERE` runs before `SELECT` logically).
* Some databases allow alias use in `ORDER BY`.

---

### 2. `FROM`

Defines the source tables.

```sql
FROM employees
```

#### ⚠ Caveat:

* This is where table resolution happens.
* Subqueries and CTEs are resolved here.

---

### 3. `JOIN`

Combines rows from multiple tables.

```sql
INNER JOIN departments d ON e.dept_id = d.id
```

Types:

* `INNER JOIN`
* `LEFT JOIN`
* `RIGHT JOIN`
* `FULL JOIN`
* `CROSS JOIN`

#### ⚠ Caveat:

* `JOIN` logically occurs before `WHERE`.
* Filtering in `WHERE` after a `LEFT JOIN` can accidentally turn it into an `INNER JOIN`.

---

### 4. `WHERE`

Filters rows before grouping.

```sql
WHERE salary > 50000
```

#### ⚠ Caveat:

* Cannot use aggregate functions here.
* Cannot use `SELECT` aliases.
* Operates on raw rows (before grouping).

---

### 5. `GROUP BY`

Groups rows for aggregation.

```sql
GROUP BY department_id
```

#### ⚠ Caveats:

* Every non-aggregated column in `SELECT` must appear in `GROUP BY` (in strict SQL).
* Some databases (like MySQL with loose mode) allow non-standard behavior.

---

### 6. `HAVING`

Filters after grouping.

```sql
HAVING COUNT(*) > 5
```

#### ⚠ Caveat:

* Used for aggregate filtering.
* Runs after `GROUP BY`.

---

### 7. `ORDER BY`

Sorts final result set.

```sql
ORDER BY salary DESC
```

#### ⚠ Caveat:

* Can use column aliases (in most databases).
* Executes after `SELECT`.

---

### 8. `LIMIT` / `OFFSET`

Restricts number of rows returned.

```sql
LIMIT 10 OFFSET 20
```

#### ⚠ Caveat:

* Not part of ANSI SQL standard (standard uses `FETCH FIRST n ROWS`).
* Syntax differs in:

  * PostgreSQL
  * Microsoft SQL Server (`TOP`, `OFFSET FETCH`)
  * Oracle Corporation (`FETCH FIRST`, `ROWNUM` historically)

---

## 2️⃣ Logical Execution Order (Very Important Caveat)

The written order is **NOT** the execution order.

#### Actual logical execution order:

1. `FROM`
2. `JOIN`
3. `WHERE`
4. `GROUP BY`
5. `HAVING`
6. `SELECT`
7. `ORDER BY`
8. `LIMIT`

This explains:

* Why aliases don’t work in `WHERE`
* Why aggregates don’t work in `WHERE`
* Why `HAVING` exists

---

## 3️⃣ A Good Mnemonic

To remember the **written order**:

> **"Smart Friends Wear Green Hats On Leaves"**

| Word    | Clause   |
| ------- | -------- |
| Smart   | SELECT   |
| Friends | FROM     |
| Wear    | WHERE    |
| Green   | GROUP BY |
| Hats    | HAVING   |
| On      | ORDER BY |
| Leaves  | LIMIT    |

---

If you want one including JOIN:

> **"Silly Frogs Jump Where Grass Hides Old Leaves"**

| Word   | Clause   |
| ------ | -------- |
| Silly  | SELECT   |
| Frogs  | FROM     |
| Jump   | JOIN     |
| Where  | WHERE    |
| Grass  | GROUP BY |
| Hides  | HAVING   |
| Old    | ORDER BY |
| Leaves | LIMIT    |

---

## 4️⃣ Bonus: Other Clauses You May Encounter

#### `WITH` (CTE)

```sql
WITH temp AS (...)
SELECT ...
```

Runs before the main query.

---

#### `DISTINCT`

```sql
SELECT DISTINCT name
```

Removes duplicates (applied after SELECT projection logically).

---

#### `UNION / UNION ALL`

Combines multiple SELECT queries.

---

## 5️⃣ Practical Mental Model (Best Way to Remember)

Think in data pipeline form:

```
Tables → Join → Filter rows → Group → Filter groups → Pick columns → Sort → Trim rows
```

If you internalize that pipeline, you’ll never forget clause order again.

---

If you'd like, I can also give you:

* A visual execution diagram
* A tricky interview question based on clause order
* Or advanced caveats (window functions, subquery scoping, correlated queries)


## Caveats

---

### 🔥 Tricky Question: Why Does This Query Fail?

Consider this table:

```sql
employees(id, name, department_id, salary)
```

Now look at this query:

```sql
SELECT department_id, COUNT(*) AS emp_count
FROM employees
WHERE emp_count > 5
GROUP BY department_id;
```

##### ❓ Question:

Why does this query fail?

---

### ✅ Correct Answer (What Interviewers Expect)

It fails because:

* `WHERE` runs **before** `GROUP BY`
* `emp_count` is created in the `SELECT` clause
* Aggregation (`COUNT(*)`) happens during `GROUP BY`
* At the time `WHERE` executes, `emp_count` does not exist

##### Logical execution order:

1. `FROM employees`
2. `WHERE emp_count > 5` ❌ (problem: emp_count not defined yet)
3. `GROUP BY department_id`
4. `SELECT department_id, COUNT(*)`

So the database throws an error.

---

### ✅ Correct Version

```sql
SELECT department_id, COUNT(*) AS emp_count
FROM employees
GROUP BY department_id
HAVING COUNT(*) > 5;
```

##### Why this works:

* `GROUP BY` creates grouped rows
* `HAVING` filters groups
* `COUNT(*)` exists at this stage

---

### 🔥 Second-Level Trick (Even Better Interview Trap)

Now consider this query:

```sql
SELECT name, salary
FROM employees
WHERE salary > AVG(salary);
```

##### ❓ Why does this fail?

Because:

* `WHERE` runs before aggregation
* `AVG(salary)` requires aggregation
* Aggregation happens after `GROUP BY`

So aggregate functions cannot be used in `WHERE`.

---

### ✅ Correct Solutions

##### Option 1: Subquery

```sql
SELECT name, salary
FROM employees
WHERE salary > (
    SELECT AVG(salary) FROM employees
);
```

##### Option 2: Window Function (Advanced Answer)

```sql
SELECT name, salary
FROM (
    SELECT name, salary, AVG(salary) OVER () AS avg_salary
    FROM employees
) t
WHERE salary > avg_salary;
```

If a candidate mentions window functions, that’s usually a strong signal of deeper SQL understanding.

---

### 🔥 Ultra-Trick (LEFT JOIN Trap)

Consider:

```sql
SELECT d.name, COUNT(e.id)
FROM departments d
LEFT JOIN employees e ON d.id = e.department_id
WHERE e.salary > 50000
GROUP BY d.name;
```

##### ❓ What’s wrong here?

This query **accidentally converts the LEFT JOIN into an INNER JOIN.**

Why?

Because `WHERE e.salary > 50000` removes rows where `e` is `NULL`.

Departments with zero employees disappear.

---

##### ✅ Correct Version

Move condition into the `JOIN`:

```sql
SELECT d.name, COUNT(e.id)
FROM departments d
LEFT JOIN employees e 
    ON d.id = e.department_id 
    AND e.salary > 50000
GROUP BY d.name;
```

---

### 🎯 What This Tests

These questions test whether you truly understand:

```
FROM → JOIN → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT
```

If someone memorized syntax but doesn’t understand logical execution order, they fail here.

---



### 1. Trying to use a SELECT alias in the WHERE clause (most classic gotcha)

**Why it fails**  
WHERE runs **before** SELECT → aliases don't exist yet.

```sql
-- ❌ This fails ("column annual_salary does not exist" or similar)
SELECT salary * 12 AS annual_salary
FROM employees
WHERE annual_salary > 60000;
```

**Correct ways** (choose based on readability/performance):

```sql
-- Option A: Repeat the expression
SELECT salary * 12 AS annual_salary
FROM employees
WHERE salary * 12 > 60000;

-- Option B: Use a subquery / CTE (cleaner for complex expressions)
WITH cte AS (
  SELECT *, salary * 12 AS annual_salary
  FROM employees
)
SELECT *
FROM cte
WHERE annual_salary > 60000;
```

### 2. Trying to filter on an aggregate in WHERE instead of HAVING

**Why it fails**  
Aggregates (COUNT, SUM, AVG, etc.) are computed **during/after GROUP BY**, but **WHERE** only sees individual rows (pre-grouping).

```sql
-- ❌ Fails or gives wrong result
SELECT department, COUNT(*) AS emp_count
FROM employees
WHERE COUNT(*) > 5          -- invalid use of aggregate
GROUP BY department;
```

**Correct**:

```sql
-- Use HAVING (runs after GROUP BY)
SELECT department, COUNT(*) AS emp_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

Very frequent mistake when people first learn GROUP BY.

### 3. WHERE vs HAVING confusion even without aggregates

```sql
-- This keeps only departments that have >5 employees *after* filtering active ones
SELECT department, COUNT(*) 
FROM employees
WHERE status = 'active'
GROUP BY department
HAVING COUNT(*) > 5;

-- This is different: only counts active employees per dept, then filters depts with >5
-- (same in this case, but order matters conceptually)
```

People sometimes put row-level filters in HAVING by mistake — it works but is less efficient (HAVING filters groups, not rows).

### 4. Using window functions / analytic functions in WHERE

Window functions (ROW_NUMBER(), RANK(), LAG(), etc.) are evaluated **in the SELECT phase** (after FROM/WHERE/GROUP BY/HAVING).

```sql
-- ❌ Fails
SELECT employee_id, salary,
       ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) AS rn
FROM employees
WHERE rn = 1;   -- rn doesn't exist yet
```

**Fixes**:

```sql
-- Use CTE / subquery
WITH ranked AS (
  SELECT *, ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) AS rn
  FROM employees
)
SELECT * FROM ranked WHERE rn = 1;

-- Or use QUALIFY (Snowflake/BigQuery/Databricks syntax — not standard SQL)
SELECT *
FROM employees
QUALIFY ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) = 1;
```

### 5. ORDER BY can use aliases — but people forget and repeat expressions unnecessarily

This actually works (because ORDER BY is last):

```sql
SELECT salary * 12 AS annual_salary
FROM employees
ORDER BY annual_salary DESC;   -- ✅ works
```

Many people unnecessarily write `ORDER BY salary * 12 DESC` out of habit from the WHERE gotcha.

### 6. GROUP BY must include all non-aggregated columns from SELECT (or use ANY_VALUE / functional dependency in some engines)

This is more of a standard SQL rule, but execution order explains *why* it matters:

```sql
-- ❌ In strict mode (most databases)
SELECT department, manager_name, COUNT(*)
FROM employees
GROUP BY department;   -- manager_name is not aggregated nor in GROUP BY
```

You either GROUP BY manager_name too (if it’s constant per department), or aggregate it.

### Quick Summary Table of Gotchas

| Gotcha | Clause that causes issue | Why? (timing)                  | Quick Fix                     |
|-------|---------------------------|--------------------------------|-------------------------------|
| Alias in WHERE              | WHERE                     | Before SELECT                  | Repeat expr or CTE/subquery   |
| Aggregate in WHERE          | WHERE                     | Before GROUP BY / aggregates   | Move to HAVING                |
| Window fn in WHERE          | WHERE                     | Before SELECT (window phase)   | CTE + filter after            |
| Forgetting HAVING exists    | HAVING                    | After GROUP BY                 | Use HAVING for group filters  |
| ORDER BY alias surprise     | ORDER BY                  | After SELECT                   | You *can* use aliases here!   |

Mastering these will save you tons of debugging time.  
Which one have you run into most often — or want a deeper example of?



# MCQs and Practice questions:

## MCQs

### Window Functions
[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Window function\|SQL questions#Window function]]
[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Tables\|tables]]

```quiz
type: radio
content: >-
    Which SQL clause is used to define a window function's partitioning and ordering?

options:
- content: GROUP BY clause
  feedback: The GROUP BY clause is used for aggregation that collapses rows, not for defining window function behavior.

- content: WINDOW clause
  feedback: While some databases support a WINDOW clause for naming window specifications, it's not the primary clause for defining partitioning and ordering within the OVER() clause.

- content: OVER clause
  feedback: Correct! The OVER() clause is where you define PARTITION BY, ORDER BY, and ROWS/RANGE specifications for window functions.
  correct: true

- content: HAVING clause
  feedback: HAVING is used to filter grouped results, not to define window function behavior.
```

```quiz
type: radio
content: >-
    What is the main difference between ROW_NUMBER() and RANK() window functions?

options:
- content: ROW_NUMBER() always produces consecutive numbers, while RANK() leaves gaps for ties.
  feedback: Correct! ROW_NUMBER() assigns unique sequential integers (1, 2, 3...), while RANK() gives the same rank to ties and skips numbers (1, 1, 3...).
  correct: true

- content: ROW_NUMBER() works with strings, while RANK() only works with numbers.
  feedback: Both functions work with ordered data regardless of data type.

- content: RANK() is faster than ROW_NUMBER().
  feedback: Performance depends on the database implementation and query, not inherently on which function you use.

- content: ROW_NUMBER() requires PARTITION BY, while RANK() doesn't.
  feedback: Both functions can be used with or without PARTITION BY.
```

```quiz
type: radio
content: >-
    When using LAG() or LEAD() functions, what happens if you try to access a non-existent row?

options:
- content: It throws an error.
  feedback: Window functions typically don't throw errors for boundary conditions like this.

- content: It returns NULL.
  feedback: Correct! By default, LAG() and LEAD() return NULL when there's no previous/next row in the partition.
  correct: true

- content: It returns 0 for numbers or empty string for text.
  feedback: These functions return NULL by default, though you can specify a different default value.

- content: It repeats the current row's value.
  feedback: Window functions don't automatically repeat values when reaching boundaries.
```

```quiz
type: radio
content: >-
    Which of these calculates a cumulative total within each partition?

options:
- content: SUM(sales) OVER (PARTITION BY region)
  feedback: This gives the total per region for each row, but not cumulative.

- content: SUM(sales) OVER (PARTITION BY region ORDER BY date)
  feedback: Correct! Adding ORDER BY to SUM() creates a running/cumulative total within each partition.
  correct: true

- content: SUM(sales) OVER (ORDER BY date)
  feedback: This creates a cumulative total, but not partitioned by region.

- content: SUM(sales) OVER ()
  feedback: This calculates the overall total across all rows.
```


> [!question]- Why is `SUM(sales) OVER (PARTITION BY region)` wrong. I thought `ORDER BY` has not affect on aggregation functions. It is only need for ranking, Navigation(Positional) etc.
> 
> I can see why that’s confusing! It’s a very common "gotcha" because aggregate functions like `SUM()` and `AVG()` behave like chameleons depending on whether `ORDER BY` is present.
> 
> While you are right that `ORDER BY` isn't _required_ for the math to work (unlike `RANK()`), its presence completely changes the **Window Frame** (the set of rows the function looks at).
> 
> ---
> 
> ## Why the first option is "wrong"
> 
> In the context of a **cumulative (running) total**, the first option fails because:
> 
> - **`SUM(sales) OVER (PARTITION BY region)`**: Without an `ORDER BY`, the "frame" is the entire partition. Every row in the 'North' region will show the same grand total for the North region. It's a static summary, not a step-by-step accumulation.
>     
> - **`SUM(sales) OVER (PARTITION BY region ORDER BY date)`**: The moment you add `ORDER BY`, the default frame shifts. It now means: _"Sum everything from the very first row of this partition up to the current row."_
>     
> 
> ---
> 
> ## How `ORDER BY` transforms Aggregates
> 
> Think of it as the difference between looking at a **receipt total** vs. a **bank statement**:
> 
> |**Query**|**Logic**|**Result Type**|
> |---|---|---|
> |`SUM(sales) OVER (PARTITION BY region)`|Look at all rows in the group at once.|**Group Total**|
> |`SUM(sales) OVER (PARTITION BY region ORDER BY date)`|Look at rows one by one in sequence.|**Running Total**|
> 
> ---
> 
> ## The "Invisible" Default
> 
> When you include `ORDER BY` in an aggregate window function, SQL secretly adds this instruction:
> 
> `RANGE BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW`
> 
> This is why the image you shared marks the second option as correct. To get a **cumulative** total, you need that "one-row-at-a-time" progression that only `ORDER BY` provides.
> 
> ### Quick Test for You
> 
> If you used `SUM(salary) OVER ()` (no partition, no order) on your `empsalary` table, what value do you think would appear on every single row?
> 
> _(Hint: It involves every employee in the table!)_

```quiz
type: radio
content: >-
    What does the FRAME clause (ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) specify?

options:
- content: Only the current row
  feedback: This would be ROWS BETWEEN CURRENT ROW AND CURRENT ROW.

- content: All rows in the partition up to and including the current row
  feedback: Correct! UNBOUNDED PRECEDING means from the start of the partition, CURRENT ROW means up to the current row.
  correct: true

- content: The next 5 rows only
  feedback: This would be ROWS BETWEEN CURRENT ROW AND 5 FOLLOWING or similar.

- content: All rows in the entire result set
  feedback: This would require no frame clause or different specifications.
```

```quiz
type: radio
content: >-
    How does PARTITION BY differ from GROUP BY in SQL?

options:
- content: PARTITION BY is used in window functions and doesn't reduce rows, while GROUP BY reduces rows.
  feedback: Correct! Window functions with PARTITION BY compute values per row within partitions, while GROUP BY aggregates and collapses rows.
  correct: true

- content: They are identical and can be used interchangeably.
  feedback: They serve fundamentally different purposes and produce different results.

- content: PARTITION BY is faster than GROUP BY.
  feedback: Performance depends on many factors including data size, indexes, and database optimization.

- content: GROUP BY can only be used with aggregate functions, while PARTITION BY works with any function.
  feedback: GROUP BY is specifically for aggregation, but PARTITION BY only works with window functions.
```

```quiz
type: radio
content: >-
    Which window function would you use to find the first value in each partition?

options:
- content: MIN()
  feedback: MIN() returns the smallest value, not necessarily the first value based on ordering.

- content: FIRST()
  feedback: There's no FIRST() function in standard SQL window functions.

- content: FIRST_VALUE()
  feedback: Correct! FIRST_VALUE() returns the first value in the window frame according to the specified order.
  correct: true

- content: ROW_NUMBER() with a filter
  feedback: While you could use ROW_NUMBER() = 1 with a subquery, FIRST_VALUE() is the dedicated function for this.
```

```quiz
type: checkbox
content: >-
    Which of the following are valid uses of window functions? (Select all that apply)

options:
- content: Calculating running totals
  feedback: Correct! Window functions like SUM() with ORDER BY are perfect for running totals.
  correct: true

- content: Comparing each row to aggregate values (like above/below average)
  feedback: Correct! Window functions let you include aggregates alongside individual rows.
  correct: true

- content: Creating pivot tables
  feedback: Pivoting typically uses CASE statements or PIVOT operators, not window functions.

- content: Ranking rows within categories
  feedback: Correct! Functions like ROW_NUMBER(), RANK(), and DENSE_RANK() are ideal for this.
  correct: true

- content: Joining tables
  feedback: Window functions operate on result sets, they don't replace JOIN operations.
```


### PostgreSQL Indexing Quiz

#### Multiple Choice Questions

```quiz
type: radio
content: >-
    What is the primary purpose of database indexing in PostgreSQL?

options:
- content: To enforce data integrity constraints
  feedback: While unique indexes can enforce uniqueness, that's not the primary purpose. Data integrity is typically enforced via constraints, not indexes.

- content: To allow faster data retrieval without scanning entire tables
  feedback: Correct! Indexes create efficient lookup structures that allow PostgreSQL to find rows quickly without sequential scans.
  correct: true

- content: To reduce storage space requirements
  feedback: Actually, indexes consume additional storage space. They trade storage for speed.

- content: To automatically optimize SQL queries
  feedback: Indexes don't optimize queries automatically; the query planner decides when to use them.
```

```quiz
type: radio
content: >-
    Which index type is the DEFAULT in PostgreSQL and supports range queries?

options:
- content: Hash Index
  feedback: Hash indexes only support equality operations, not range queries.

- content: B-Tree Index
  feedback: Correct! B-Tree is the default index type in PostgreSQL and supports =, <, >, BETWEEN, and other range operations.
  correct: true

- content: GIN Index
  feedback: GIN indexes are specialized for multi-valued data like arrays and JSON, not general range queries.

- content: GiST Index
  feedback: GiST indexes are used for geometric and proximity searches, not as the default for general range queries.
```

```quiz
type: radio
content: >-
    Which of these operations will be slowed down by adding more indexes?

options:
- content: SELECT queries
  feedback: SELECT queries are typically sped up by indexes, not slowed down.

- content: INSERT, UPDATE, and DELETE operations
  feedback: Correct! DML operations slow down because indexes must be maintained/updated when data changes.
  correct: true

- content: CREATE TABLE statements
  feedback: Indexes don't affect table creation, only data manipulation.

- content: EXPLAIN ANALYZE commands
  feedback: EXPLAIN ANALYZE shows execution plans but isn't affected by index count.
```

```quiz
type: radio
content: >-
    When should you consider using a partial index?

options:
- content: When you need to index all rows in a table
  feedback: Partial indexes specifically exclude some rows based on a WHERE clause.

- content: When you need to speed up queries that filter by a specific condition
  feedback: Correct! Partial indexes are smaller and faster because they only index rows matching a WHERE condition.
  correct: true

- content: When you need to enforce uniqueness across all rows
  feedback: Unique constraints/indexes enforce uniqueness; partial indexes can be unique but only for the filtered rows.

- content: When you're working with JSONB data
  feedback: JSONB data typically uses GIN indexes, not necessarily partial indexes.
```

#### Checkbox Questions (Multiple Correct Answers)

```quiz
type: checkbox
content: >-
    Which of these are valid PostgreSQL index types? (Select all that apply)

options:
- content: B-Tree
  feedback: Correct! B-Tree is the default and most common index type.
  correct: true

- content: Hash
  feedback: Correct! Hash indexes exist but are rarely used.
  correct: true

- content: GIN
  feedback: Correct! GIN indexes are for multi-valued data like arrays and JSONB.
  correct: true

- content: GiST
  feedback: Correct! GiST indexes are for geometric and proximity searches.
  correct: true

- content: BRIN
  feedback: Correct! BRIN indexes are for large, naturally ordered tables.
  correct: true

- content: Binary Tree
  feedback: While B-Tree stands for "Balanced Tree", PostgreSQL doesn't have a separate "Binary Tree" index type.

- content: Linear Index
  feedback: This is not a valid PostgreSQL index type.
```

```quiz
type: checkbox
content: >-
    Which of these are good candidates for indexing? (Select all that apply)

options:
- content: Primary key columns
  feedback: Correct! Primary keys are automatically indexed and frequently used in joins.
  correct: true

- content: Foreign key columns
  feedback: Correct! Foreign keys are often used in JOIN operations.
  correct: true

- content: Columns frequently used in WHERE clauses
  feedback: Correct! These are prime candidates for indexing.
  correct: true

- content: Boolean columns with only 2 possible values
  feedback: Generally not good for indexing due to low cardinality (poor selectivity).
  
- content: Columns used in ORDER BY clauses
  feedback: Correct! Indexes can prevent expensive sort operations.
  correct: true

- content: All columns in every table
  feedback: This would cause massive write performance issues and isn't practical.
```

#### Practical Application Questions

```quiz
type: noodle
content: >-
    Match each index type with its best use case.

options:
- content: Equality-only lookups on large datasets
- content: Full-text search and JSONB queries
- content: Range queries and general purpose indexing
- content: Geographic location queries
- content: Time-series data with natural ordering

questions:
- content: B-Tree Index
  correct: Range queries and general purpose indexing

- content: Hash Index
  correct: Equality-only lookups on large datasets

- content: GIN Index
  correct: Full-text search and JSONB queries

- content: GiST Index
  correct: Geographic location queries

- content: BRIN Index
  correct: Time-series data with natural ordering
```

```quiz
type: radio
content: |
    Given this table and query, which index would be most effective?
    ```
    CREATE TABLE orders (
        id SERIAL PRIMARY KEY,
        customer_id INTEGER,
        order_date DATE,
        status VARCHAR(20),
        amount NUMERIC
    );
    
    -- Frequent query:
    SELECT * FROM orders 
    WHERE customer_id = 123 
      AND status = 'shipped'
    ORDER BY order_date DESC;
    ```

options:
- content: CREATE INDEX idx_orders_customer ON orders(customer_id);
  feedback: This helps but doesn't cover the status filter or ordering.

- content: CREATE INDEX idx_orders_status ON orders(status);
  feedback: This has poor selectivity (status has few distinct values) and doesn't help with customer_id.

- content: CREATE INDEX idx_orders_date ON orders(order_date);
  feedback: This helps with ORDER BY but not the WHERE clause.

- content: CREATE INDEX idx_orders_customer_status_date ON orders(customer_id, status, order_date DESC);
  feedback: "Correct! This composite index covers all aspects: filtering on customer_id and status, plus ordering by order_date."
  correct: true
```

```quiz
type: radio
content: >-
    Why might a query not use an available index? (Choose the BEST reason)

options:
- content: The index is on the wrong columns
  feedback: This could be true, but it's not the most common reason.

- content: The table is too small
  feedback: Correct! For very small tables, sequential scans can be faster than index lookups.
  correct: true

- content: The index name doesn't match the column name
  feedback: PostgreSQL doesn't require index names to match column names.

- content: The query doesn't have a WHERE clause
  feedback: While true for some queries, even queries without WHERE can use indexes for ORDER BY.
```

```quiz
type: checkbox
content: >-
    Which statements are TRUE about composite (multi-column) indexes? (Select all that apply)

options:
- content: Column order matters in composite indexes
  feedback: Correct! Queries can only use a composite index if they reference columns from left to right.
  correct: true

- content: A composite index on (a, b) can be used for queries filtering only on column b
  feedback: Incorrect. The query must include column a (or both a and b) to use this index.

- content: Composite indexes are always larger than single-column indexes
  feedback: Correct! They include more data per index entry.
  correct: true

- content: PostgreSQL can use multiple single-column indexes together via bitmap scans
  feedback: Correct! PostgreSQL can combine multiple indexes using bitmap index scans.
  correct: true

- content: A composite index is always better than multiple single-column indexes
  feedback: Incorrect. It depends on the query patterns. Sometimes multiple single-column indexes are more flexible.
```

```quiz
type: text
content: >-
    When analyzing query performance, what command should you use to see if and how PostgreSQL is using indexes?

# optional reference answer shown after pressing [Check]
correct: >-
    Use EXPLAIN ANALYZE followed by your query. This shows the execution plan and whether indexes are being used, along with timing information.
```

### Basic Join Quizzes

[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Joins\|SQL questions#Joins]]
> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |
> 

```quiz
type: radio
content: |
    What type of JOIN would you use to list all departments (including 'hr') along with their employees, showing NULL for departments with no employees?

options:
- content: INNER JOIN from departments to empsalary
  feedback: INNER JOIN would only show departments that have matching employees, so 'hr' department would be excluded.

- content: LEFT JOIN from departments to empsalary
  feedback: Correct! A LEFT JOIN from departments to empsalary would show all departments, including those without employees.
  correct: true

- content: RIGHT JOIN from departments to empsalary
  feedback: A RIGHT JOIN from departments to empsalary would show all employees and only departments that have employees.

- content: FULL OUTER JOIN from departments to empsalary
  feedback: This would work too, but it's not the most efficient choice since we want all departments specifically.
```

```quiz
type: checkbox
content: |
    Which of these queries correctly join the empsalary and departments tables to show employee details with department information?
    (Select all that apply)

options:
- content: |
    SELECT e.depname, e.empno, e.salary, d.dept_name, d.manager
    FROM empsalary e
    INNER JOIN departments d ON e.depname = d.dept_code;
  feedback: Correct! This uses an INNER JOIN to match employees with their departments.
  correct: true

- content: |
    SELECT e.depname, e.empno, e.salary, d.dept_name, d.manager
    FROM empsalary e, departments d
    WHERE e.depname = d.dept_code;
  feedback: Correct! This is the old-style implicit join syntax that works like INNER JOIN.
  correct: true

- content: |
    SELECT e.depname, e.empno, e.salary, d.dept_name, d.manager
    FROM empsalary e
    CROSS JOIN departments d;
  feedback: Incorrect! CROSS JOIN produces a Cartesian product (all combinations), not matching rows.

- content: |
    SELECT d.dept_code, d.dept_name, e.empno, e.salary
    FROM departments d
    LEFT JOIN empsalary e ON d.dept_code = e.depname;
  feedback: Correct! This shows all departments including those without employees.
  correct: true
```

```quiz
type: noodle
content: |
    Match each JOIN type with its description.

options:
- content: Returns only matching rows from both tables
- content: Returns all rows from left table, matched rows from right
- content: Returns all rows from right table, matched rows from left
- content: Returns all rows from both tables

questions:
- content: INNER JOIN
  correct: Returns only matching rows from both tables

- content: LEFT JOIN
  correct: Returns all rows from left table, matched rows from right

- content: RIGHT JOIN
  correct: Returns all rows from right table, matched rows from left

- content: FULL OUTER JOIN
  correct: Returns all rows from both tables
```

> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |
 
```quiz
type: radio
content: |
    How many rows would this query return?
    ```
    SELECT d.dept_code, d.dept_name, e.empno
    FROM departments d
    LEFT JOIN empsalary e ON d.dept_code = e.depname;
    ```

options:
- content: "7"
  feedback: That's the number of employees, but we're starting with departments.

- content: "8" 
  feedback: That's the number of employees plus 1, but we need to think about department count.

- content: "6"
  feedback: There are 4 departments and 8 employees, but some departments have multiple employees.

- content: "9"
  feedback: "Let's count: 'sales' has 3 employees, 'IT' has 3, 'support' has 2, 'hr' has 0 (shows as NULL). Total = 3+3+2+1 = 9 rows."
  correct: true
```

## Practice
### Window Functions
[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Tables\|tables]]

```quiz
type: radio
content: >-
    Given the `empsalary` table, which query would rank employees within each department by salary from highest to lowest?

options:
- content: |
    SELECT depname, empno, salary,
           RANK() OVER (ORDER BY salary DESC) as rank
    FROM empsalary;
  feedback: This query ranks all employees globally by salary, not within each department. It lacks PARTITION BY depname.

- content: |
    SELECT depname, empno, salary,
           RANK() OVER (PARTITION BY depname ORDER BY salary) as rank
    FROM empsalary;
  feedback: This partitions by department but orders by salary ascending (lowest first). The DESC keyword is missing.

- content: |
    SELECT depname, empno, salary,
           RANK() OVER (PARTITION BY depname ORDER BY salary DESC) as rank
    FROM empsalary;
  feedback: Correct! This partitions by department and ranks within each department from highest to lowest salary.
  correct: true

- content: |
    SELECT depname, empno, salary,
           ROW_NUMBER() OVER (PARTITION BY depname) as rank
    FROM empsalary;
  feedback: This partitions by department but has no ORDER BY clause, so the ranking order is unpredictable.
```

> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |

```quiz
type: radio
content: |
    What would the following query return for the employee with `empno=11 (sales, 5200)`? 
    
    ```
    SELECT depname, empno, salary,
           SUM(salary) OVER (PARTITION BY depname ORDER BY salary) as running_total
    FROM empsalary
    ORDER BY depname, salary;
    ```

options:
- content: |
    5200
  feedback: This would be just his salary, not the running total.

- content: |
    9000
  feedback: "This is the total for all sales employees (5000+4800)"

- content: |
    15000
  feedback: "Correct! The running total within sales department ordered by salary ascending: (5000+4800+5200)=15000 when it reaches 5200."
  correct: true

- content: |
    10000
  feedback: This might be if you included 5200 in the sum, but running totals are calculated up to the current row.
```

> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |

```quiz
type: radio
content: |
    What would the `LAG()` function return in this query for `empno=3 (IT, 6000)`?
    
    ```
    SELECT depname, empno, salary,
           LAG(salary) OVER (PARTITION BY depname ORDER BY empno) as prev_salary
    FROM empsalary;
    ```

options:
- content: "NULL"
  feedback: Correct! Since empno=3 is the first employee in the IT department when ordered by empno, there is no previous row, so LAG() returns NULL.
  correct: true

- content: "7700"
  feedback: 7700 is empno=4's salary, which comes after empno=5 when ordered by empno ascending.

- content: "6000"
  feedback: 6000 is empno=3's salary, but it's in a different position in the ordering.

- content: "8000"
  feedback: This would be the current salary, not the previous one.
```

```quiz
type: checkbox
content: >-
    Which of these queries would show each employee's salary along with the average salary of their department?

options:
- content: |
    SELECT depname, empno, salary,
           AVG(salary) FROM empsalary
    GROUP BY depname;
  feedback: This query won't work as written - empno and salary aren't in GROUP BY. Even if fixed, it would collapse rows.

- content: |
    SELECT depname, empno, salary,
           AVG(salary) OVER (PARTITION BY depname) as dept_avg
    FROM empsalary;
  feedback: Correct! This uses a window function to calculate department average without collapsing rows.
  correct: true

- content: |
    SELECT e.depname, e.empno, e.salary, d.avg_salary
    FROM empsalary e
    JOIN (SELECT depname, AVG(salary) as avg_salary 
          FROM empsalary GROUP BY depname) d
    ON e.depname = d.depname;
  feedback: Correct! This uses a subquery join to achieve the same result as a window function.
  correct: true

- content: |
    SELECT depname, empno, salary,
           AVG(salary) OVER () as overall_avg
    FROM empsalary;
  feedback: This calculates the overall average across all departments, not department-specific averages.
```


```quiz
type: radio
content: >-
    Which query would show the difference between each employee's salary and the next highest salary in their department?

options:
- content: |
    SELECT depname, empno, salary,
           salary - LAG(salary) OVER (PARTITION BY depname ORDER BY salary DESC) as diff
    FROM empsalary;
  feedback: Correct! LAG() with ORDER BY salary DESC gets the previous (higher) salary, so subtracting gives the difference.
  correct: true

- content: |
    SELECT depname, empno, salary,
           salary - LEAD(salary) OVER (PARTITION BY depname ORDER BY salary) as diff
    FROM empsalary;
  feedback: This would compare with the next higher salary only if ordered ascending, but LEAD looks forward, not backward.

- content: |
    SELECT depname, empno, salary,
           MAX(salary) OVER (PARTITION BY depname) - salary as diff
    FROM empsalary;
  feedback: This shows difference from department maximum, not the next highest salary.

- content: |
    SELECT depname, empno, salary,
           salary - RANK() OVER (PARTITION BY depname ORDER BY salary DESC) as diff
    FROM empsalary;
  feedback: RANK() returns a rank number, not a salary value to subtract.
```

> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |

```quiz
type: radio
content: |
    What would the `NTH_VALUE()` function return in this query for `empno=1 (sales, 5000)`?
    ```
    SELECT depname, empno, salary,
           NTH_VALUE(salary, 2) OVER (
               PARTITION BY depname 
               ORDER BY salary DESC
               ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING
           ) as second_highest
    FROM empsalary;
    ```

options:
- content: "NULL"
  feedback: There is a second highest salary in sales department (5000), so not NULL.

- content: "5200"
  feedback: 5200 is the highest salary in sales, not the second highest.

- content: "5000"
  feedback: Correct! When ordered by salary DESC, the second row in sales has salary 5000.
  correct: true

- content: "4800"
  feedback: 4800 is the third highest, not the second.
```

```quiz
type: checkbox
content: >-
    Which queries would correctly show the highest paid employee in each department?

options:
- content: |
    SELECT depname, empno, salary
    FROM empsalary
    WHERE salary = MAX(salary) OVER (PARTITION BY depname);
  feedback: Window functions can't be used in WHERE clauses directly like this.

- content: |
    SELECT depname, empno, salary
    FROM (
        SELECT depname, empno, salary,
               RANK() OVER (PARTITION BY depname ORDER BY salary DESC) as rnk
        FROM empsalary
    ) ranked
    WHERE rnk = 1;
  feedback: Correct! This uses a subquery with RANK() and filters for rank 1.
  correct: true

- content: |
    SELECT DISTINCT 
        depname,
        FIRST_VALUE(empno) OVER (PARTITION BY depname ORDER BY salary DESC) as top_emp,
        FIRST_VALUE(salary) OVER (PARTITION BY depname ORDER BY salary DESC) as top_salary
    FROM empsalary;
  feedback: Correct! FIRST_VALUE gets the first (highest) salary, and DISTINCT removes duplicates.
  correct: true

- content: |
    SELECT depname, empno, salary
    FROM empsalary e1
    WHERE salary = (
        SELECT MAX(salary)
        FROM empsalary e2
        WHERE e2.depname = e1.depname
    );
  feedback: Correct! This uses a correlated subquery instead of window functions.
  correct: true
```

> [!question]- How does this works does the subquery works like inner loop ?
> 
> Yes, you hit the nail on the head! In this specific query, the subquery acts exactly like an **inner loop** in traditional programming.
> 
> This is called a **Correlated Subquery**. It is "correlated" because the inner query depends on a value from the outer query to execute.
> 
> ---
> 
> ## 1. The Execution "Mental Model"
> 
> If you were writing this in Python or Java, it would look like this:
> 
> Python
> 
> ```
> results = []
> for e1 in empsalary: # Outer Loop
>     # The Inner Loop (Subquery) runs for every single row of e1
>     max_sal = max(e2.salary for e2 in empsalary if e2.depname == e1.depname)
>     
>     if e1.salary == max_sal:
>         results.append(e1)
> ```
> 
> ### Step-by-Step for your data:
> 
> 1. **Row 1 (Outer):** `depname='sales'`, `salary=5200`.
>     
>     - **Inner Subquery:** "What is the `MAX(salary)` where `depname` is 'sales'?"
>         
>     - **Result:** 5200.
>         
>     - **Check:** Does 5200 = 5200? **Yes.** (Keep this row).
>         
> 2. **Row 2 (Outer):** `depname='sales'`, `salary=5000`.
>     
>     - **Inner Subquery:** "What is the `MAX(salary)` where `depname` is 'sales'?"
>         
>     - **Result:** 5200.
>         
>     - **Check:** Does 5000 = 5200? **No.** (Discard).
>         
> 3. **Row 4 (Outer):** `depname='IT'`, `salary=8000`.
>     
>     - **Inner Subquery:** "What is the `MAX(salary)` where `depname` is 'IT'?"
>         
>     - **Result:** 8000.
>         
>     - **Check:** Does 8000 = 8000? **Yes.** (Keep this row).
>         
> 
> ---
> 
> ## 2. Performance Note (The "O(n²)" Trap)
> 
> Because the subquery runs for **every single row** in the table, this can be slow on very large tables.
> 
> - If you have 1,000 rows, the DB might perform 1,000 sub-lookups.
>     
> - If you have 1,000,000 rows, performance will tank.
>     
> 
> ---
> 
> ## 3. The "Modern" Way (Window Functions)
> 
> Earlier we talked about window functions like `NTH_VALUE()`. You can achieve the same result as your loop without the "inner loop" overhead by using `RANK()` or `MAX() OVER()`:
> 
> SQL
> 
> ```
> SELECT depname, empno, salary
> FROM (
>     SELECT depname, empno, salary,
>            MAX(salary) OVER(PARTITION BY depname) as top_salary
>     FROM empsalary
> ) AS sub
> WHERE salary = top_salary;
> ```
> 
> **Why this is better:**
> 
> PostgreSQL only has to scan the `empsalary` table **once**, sort it, and find the max. It avoids the "looping" behavior entirely, making it much faster for big data.
> 
> ---
> 
> ## 4. Summary of your query
> 
> - **e1**: The "Pointer" currently looking at a specific row.
>     
> - **e2**: The "Scanner" that looks at the whole table to find the max for e1's department.
>     
> - **The Link**: `e2.depname = e1.depname` is what ties the scanner to the pointer.
>     
> 
> **Would you like me to show you how to use a CTE to make this "Top Salary per Department" logic even more readable?**

```quiz
type: radio
content: >-
    What percentage of the department's total salary does each employee earn? Which query calculates this?

options:
- content: |
    SELECT depname, empno, salary,
           salary / SUM(salary) OVER () * 100 as pct
    FROM empsalary;
  feedback: This calculates percentage of total company salary, not department salary.

- content: |
    SELECT depname, empno, salary,
           salary / SUM(salary) OVER (PARTITION BY depname) * 100 as pct
    FROM empsalary;
  feedback: Correct! The SUM() is partitioned by department, so each salary is divided by its department total.
  correct: true

- content: |
    SELECT depname, empno, salary,
           salary / SUM(salary) OVER (PARTITION BY depname ORDER BY salary) * 100 as pct
    FROM empsalary;
  feedback: With ORDER BY, this becomes a running percentage, not the total department percentage.

- content: |
    SELECT depname, empno, salary,
           RATIO_TO_REPORT(salary) OVER (PARTITION BY depname) * 100 as pct
    FROM empsalary;
  feedback: While RATIO_TO_REPORT is a valid function in some databases, it's not standard SQL.
```

> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |

```quiz
type: checkbox
content: >-
    Which query shows employees making more than the average salary of their department?

options:
- content: |
    SELECT depname, empno, salary
    FROM empsalary
    WHERE salary > AVG(salary) OVER (PARTITION BY depname);
  feedback: Window functions can't be used in WHERE clauses - they're evaluated after WHERE.

- content: |
    WITH dept_stats AS (
        SELECT depname, empno, salary,
               AVG(salary) OVER (PARTITION BY depname) as dept_avg
        FROM empsalary
    )
    SELECT depname, empno, salary, dept_avg
    FROM dept_stats
    WHERE salary > dept_avg;
  feedback: Correct! This uses a CTE to calculate the average first, then filters in the main query.
  correct: true

- content: |
    SELECT depname, empno, salary
    FROM empsalary
    WHERE salary > (
        SELECT AVG(salary)
        FROM empsalary e2
        WHERE e2.depname = empsalary.depname
    );
  feedback: Correct! This uses a correlated subquery instead of window functions.
  correct: true

- content: |
    SELECT e1.depname, e1.empno, e1.salary
    FROM empsalary e1
    JOIN (
        SELECT depname, AVG(salary) as dept_avg
        FROM empsalary
        GROUP BY depname
    ) e2 ON e1.depname = e2.depname
    WHERE e1.salary > e2.dept_avg;
  feedback: Correct! This uses a join with aggregated data instead of window functions.
  correct: true
```


> [!question]- <pre><code>SELECT depname, empno, salary FROM empsalary  </br>WHERE salary > (  </br> SELECT AVG(salary) FROM empsalary e2  </br> WHERE e2.depname = empsalary.depname  </br>);</code></pre></br>How does this works ? Does the subquery(inner one) gets calculated first ?
> 
> This is a classic example of a **Correlated Subquery**. While standard subqueries often run once from the inside out, correlated subqueries work a bit differently because the inner query depends on the outer query to function.
> 
> To answer your main question: **No, the subquery does not finish completely before the outer query starts.** Instead, they work in a "loop-like" fashion.
> 
> ---
> 
> ### How it Executes (Step-by-Step)
> 
> Think of this like a `foreach` loop in programming. The database engine processes the table row by row:
> 
> 1. **Outer Query Picks a Row:** The database looks at the first row in `empsalary` (e.g., `sales | 11 | 5200`).
>     
> 2. **Inner Query Receives a Value:** It "plugs in" the `depname` from that specific row into the subquery.
>     
>     - _Logic:_ `SELECT AVG(salary) FROM empsalary e2 WHERE e2.depname = 'sales'`
>         
> 3. **Subquery Calculates:** It finds the average salary for just the 'sales' department.
>     
> 4. **Outer Query Evaluates:** It compares the original employee's salary ($5200$) against that average. If it's higher, the row is kept in the results.
>     
> 5. **Repeat:** The database moves to the next row (employee 1) and repeats the entire process.
>     
> 
> ---
> 
> ### Key Differences: Regular vs. Correlated
> 
> |**Feature**|**Regular Subquery**|**Correlated Subquery**|
> |---|---|---|
> |**Dependency**|Independent of the outer query.|Depends on values from the outer query.|
> |**Execution**|Runs **once**, and the result is used by the outer query.|Runs **once for every row** processed by the outer query.|
> |**Performance**|Generally faster for large datasets.|Can be slower because it re-executes many times.|
> 
> ### A Quick Tip on Performance
> 
> If your `empsalary` table becomes very large (thousands of rows), this specific query might slow down because it has to calculate an average over and over again. In those cases, SQL developers often use **Window Functions** to get the same result more efficiently:
> 
> SQL
> 
> ```
> SELECT depname, empno, salary
> FROM (
>   SELECT depname, empno, salary, 
>          AVG(salary) OVER (PARTITION BY depname) as avg_dept_salary
>   FROM empsalary
> ) as sub
> WHERE salary > avg_dept_salary;
> ```
> 
> Would you like me to explain how that **Window Function** version works, or perhaps help you join these results with the `departments` table to show the manager's name?

```quiz
type: checkbox
content: >-
    Which of these queries demonstrate valid uses of window frame clauses?

options:
- content: |
    SELECT depname, empno, salary,
           SUM(salary) OVER (
               PARTITION BY depname 
               ORDER BY empno
               ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING
           ) as moving_sum
    FROM empsalary;
  feedback: Correct! This calculates a 3-row moving sum (previous, current, next).
  correct: true

- content: |
    SELECT depname, empno, salary,
           AVG(salary) OVER (
               PARTITION BY depname 
               ORDER BY salary
               RANGE BETWEEN 100 PRECEDING AND 100 FOLLOWING
           ) as nearby_avg
    FROM empsalary;
  feedback: Correct! This averages salaries within ±100 of the current salary.
  correct: true

- content: |
    SELECT depname, empno, salary,
           MAX(salary) OVER (
               PARTITION BY depname 
               ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING
           ) as dept_max
    FROM empsalary;
  feedback: Correct! This gets the overall department max (same as without frame clause).
  correct: true

- content: |
    SELECT depname, empno, salary,
           LAST_VALUE(salary) OVER (
               PARTITION BY depname 
               ORDER BY empno
           ) as last_salary
    FROM empsalary;
  feedback: Without a proper frame clause, LAST_VALUE defaults to CURRENT ROW, not the actual last value.
```

### Practice with Window Functions and Joins
[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Window function\|SQL questions#Window function]]
[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Joins\|SQL questions#Joins]]
[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Tables\|tables]]

> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |

```quiz
type: checkbox
content: |
    Which query correctly shows each employee's salary along with the average salary of their department?(Multiple Choice)

options:
- content: |
    SELECT e.depname, e.empno, e.salary, 
           AVG(e.salary) OVER (PARTITION BY e.depname) as dept_avg
    FROM empsalary e;
  feedback: Correct! This uses a window function to calculate the average within each department partition.
  correct: true

- content: |
    SELECT e.depname, e.empno, e.salary, d.avg_salary
    FROM empsalary e
    JOIN (SELECT depname, AVG(salary) as avg_salary 
          FROM empsalary GROUP BY depname) d 
    ON e.depname = d.depname;
  feedback: Correct! This uses a derived table/subquery with aggregation and join.
  correct: true

- content: |
    SELECT e.depname, e.empno, e.salary, AVG(e.salary)
    FROM empsalary e
    GROUP BY e.depname, e.empno, e.salary;
  feedback: This won't work as expected - you can't mix aggregated and non-aggregated columns without window functions.

- content: |
    SELECT e.depname, e.empno, e.salary, 
           (SELECT AVG(salary) FROM empsalary WHERE depname = e.depname) as dept_avg
    FROM empsalary e;
  feedback: Correct! This uses a correlated subquery to calculate department average for each employee.
  correct: true
```

> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |

```quiz
type: checkbox
content: |
    Which of these queries would show department rankings including departments with no employees?

options:
- content: |
    SELECT d.dept_code, d.dept_name,
           RANK() OVER (ORDER BY COUNT(e.empno) DESC) as employee_count_rank
    FROM departments d
    INNER JOIN empsalary e ON d.dept_code = e.depname
    GROUP BY d.dept_code, d.dept_name;
  feedback: This uses INNER JOIN, so departments with no employees won't appear.

- content: |
    SELECT d.dept_code, d.dept_name,
           RANK() OVER (ORDER BY COUNT(e.empno) DESC) as employee_count_rank
    FROM departments d
    LEFT JOIN empsalary e ON d.dept_code = e.depname
    GROUP BY d.dept_code, d.dept_name;
  feedback: Correct! LEFT JOIN ensures all departments appear, and COUNT(e.empno) will count NULLs as 0.
  correct: true

- content: |
    SELECT d.dept_code, d.dept_name,
           COUNT(e.empno) as emp_count,
           DENSE_RANK() OVER (ORDER BY COUNT(e.empno) DESC) as rank
    FROM departments d
    LEFT JOIN empsalary e ON d.dept_code = e.depname
    GROUP BY d.dept_code, d.dept_name;
  feedback: Correct! This shows the count and rank for all departments.
  correct: true

- content: |
    SELECT d.dept_code, d.dept_name,
           COALESCE(COUNT(e.empno), 0) as emp_count
    FROM departments d
    FULL OUTER JOIN empsalary e ON d.dept_code = e.depname
    GROUP BY d.dept_code, d.dept_name;
  feedback: This would work but FULL OUTER JOIN isn't necessary here since we want all departments.
```


> [!question]- <pre><code>SELECT d.dept_code, d.dept_name,  </br>RANK() OVER (ORDER BY COUNT(e.empno) DESC) AS employee_count_rank  </br>FROM departments d  </br>LEFT JOIN empsalary e ON d.dept_code = e.depname  </br>GROUP BY d.dept_code, d.dept_name;</code></pre></br>How does this works ?
>
> Let’s walk through this **exact query**, step by step, in the order PostgreSQL _logically_ evaluates it, and clarify why the window function works even though `COUNT()` is an aggregate.
> 
> ---
> 
> ## The Query
> 
> ```sql
> SELECT
>     d.dept_code,
>     d.dept_name,
>     RANK() OVER (ORDER BY COUNT(e.empno) DESC) AS employee_count_rank
> FROM departments d
> LEFT JOIN empsalary e
>     ON d.dept_code = e.depname
> GROUP BY
>     d.dept_code,
>     d.dept_name;
> ```
> 
> ---
> 
> ## Step 1: FROM + LEFT JOIN
> 
> ```sql
> FROM departments d
> LEFT JOIN empsalary e
>     ON d.dept_code = e.depname
> ```
> 
> PostgreSQL first builds the joined row set.
> 
> **Effect of LEFT JOIN**
> 
> - Every row from `departments` appears at least once.
>     
> - Matching rows from `empsalary` are attached.
>     
> - Departments with no employees (e.g. `hr`) get `NULL` values for `e.*`.
>     
> 
> Conceptually, the joined result looks like:
> 
> ```
> sales    | Sales & Marketing      | empno 11
> sales    | Sales & Marketing      | empno 1
> sales    | Sales & Marketing      | empno 2
> IT       | Information Technology | empno 5
> IT       | Information Technology | empno 4
> IT       | Information Technology | empno 3
> support  | Customer Support       | empno 7
> support  | Customer Support       | empno 6
> hr       | Human Resources        | NULL
> ```
> 
> ---
> 
> ## Step 2: GROUP BY (Aggregation Phase)
> 
> ```sql
> GROUP BY d.dept_code, d.dept_name
> ```
> 
> Now PostgreSQL **collapses rows per department**.
> 
> For each department group:
> 
> - `COUNT(e.empno)` is computed
>     
> - `COUNT(column)` ignores `NULL`, so:
>     
>     - `hr` → count = `0`
>         
>     - others → number of employees
>         
> 
> Result after aggregation (conceptual):
> 
> |dept_code|dept_name|COUNT(e.empno)|
> |---|---|---|
> |sales|Sales & Marketing|3|
> |IT|Information Technology|3|
> |support|Customer Support|2|
> |hr|Human Resources|0|
> 
> At this point, **aggregation is complete**.
> 
> ---
> 
> ## Step 3: Window Function Evaluation
> 
> ```sql
> RANK() OVER (ORDER BY COUNT(e.empno) DESC)
> ```
> 
> This is the key part.
> 
> ### Important rule
> 
> > **Window functions are evaluated _after_ aggregation, but _before_ final output.**
> 
> So:
> 
> - `COUNT(e.empno)` is already known **per group**
>     
> - The window function does **not** re-aggregate
>     
> - It simply _looks at the grouped rows_
>     
> 
> The window sees this ordered set:
> 
> ```
> COUNT = 3 → sales
> COUNT = 3 → IT
> COUNT = 2 → support
> COUNT = 0 → hr
> ```
> 
> ### How `RANK()` works
> 
> - Same values → same rank
>     
> - Next rank is skipped
>     
> 
> Ranks assigned:
> 
> |COUNT|dept_code|rank|
> |---|---|---|
> |3|sales|1|
> |3|IT|1|
> |2|support|3|
> |0|hr|4|
> 
> ---
> 
> ## Step 4: SELECT Projection
> 
> ```sql
> SELECT d.dept_code, d.dept_name, employee_count_rank
> ```
> 
> Final output:
> 
> |dept_code|dept_name|employee_count_rank|
> |---|---|---|
> |sales|Sales & Marketing|1|
> |IT|Information Technology|1|
> |support|Customer Support|3|
> |hr|Human Resources|4|
> 
> ---
> 
> ## Why `COUNT()` Is Allowed Inside `OVER()`
> 
> This often causes confusion.
> 
> ### Key insight
> 
> > The `COUNT()` here is **not a window aggregate**  
> > It is a **group aggregate** whose result is reused by the window function.
> 
> Think of it as:
> 
> ```sql
> SELECT *,
>        RANK() OVER (ORDER BY employee_count DESC)
> FROM (
>     SELECT d.dept_code, d.dept_name,
>            COUNT(e.empno) AS employee_count
>     FROM departments d
>     LEFT JOIN empsalary e
>         ON d.dept_code = e.depname
>     GROUP BY d.dept_code, d.dept_name
> ) t;
> ```
> 
> Your query is just a **compact form** of this.
> 
> ---
> 
> ## Why This Does NOT Violate SQL Rules
> 
> - `COUNT(e.empno)` is valid because it’s aggregated
>     
> - Every non-aggregated column is in `GROUP BY`
>     
> - Window functions are applied **after** grouping
>     
> - No mixing of row-level and group-level logic
>     
> 
> ---
> 
> ## Summary (Mental Model)
> 
> 1. Join departments with employees
>     
> 2. Collapse rows per department (`GROUP BY`)
>     
> 3. Compute employee counts
>     
> 4. Rank departments by those counts using a window
>     
> 5. Output results
>     
> 
> If you want, next we can:
> 
> - Compare `RANK()` vs `DENSE_RANK()` vs `ROW_NUMBER()`
>     
> - Rewrite this using `FILTER`
>     
> - Show why this _cannot_ be done with `ORDER BY` alone
>     
> 
> Just say which direction you want to go.
> 
> > [!question]- So `COUNT()` finds the frequency of occurence ?
> > Exactly! You’ve hit the nail on the head. In SQL, `COUNT()` is the primary tool for measuring **frequency**, but it has one specific rule that often trips people up.
> > 
> > ### The "Null" Rule
> > 
> > When you use `COUNT(column_name)`, it counts how many times a **non-null** value appears in that column.
> > 
> > In your query: `COUNT(e.empno)`
> > 
> > - For **Sales**, it sees `11`, `1`, and `2`. (Frequency = **3**)
> >     
> > - For **HR**, because of the `LEFT JOIN`, the `empno` is `NULL`.
> >     
> > - `COUNT` ignores that `NULL`, giving you a frequency of **0**.
> >     
> > 
> > ---
> > 
> > ### Three Ways to use COUNT()
> > 
> > Depending on what you want to measure, you can use `COUNT` in different ways:
> > 
> > |**Usage**|**What it measures**|**In your data...**|
> > |---|---|---|
> > |**`COUNT(*)`**|Every single row in the group.|HR would show **1** (the department exists).|
> > |**`COUNT(empno)`**|Frequency of actual employees.|HR would show **0** (no employees found).|
> > |**`COUNT(DISTINCT depname)`**|Unique occurrences only.|If "sales" appeared 10 times, this would return **1**.|
> > 
> > ---
> > 
> > ### Why this matters for your Rank
> > 
> > In your specific code, the `COUNT(e.empno)` is the **input** for the rank.
> > 
> > 1. **Sales** (3) and **IT** (3) are the most frequent.
> >     
> > 2. **Support** (2) is next.
> >     
> > 3. **HR** (0) is last.
> >     
> > 
> > Because you used `ORDER BY COUNT(e.empno) DESC`, the ranker sees the frequencies as `3, 3, 2, 0` and assigns the ranks accordingly.
> > 
> > ### Quick Question for you
> > 
> > If you had two employees with the exact same ID number accidentally entered twice in the `sales` department, `COUNT(empno)` would count them both.
> > 
> > Would you like to see how to use `COUNT(DISTINCT ...)` to make sure you're only counting unique employees, just in case there are duplicates?


> [!question]- Is there an order of execution of such SQl statements like left to right or outer and then inner ?
> 
> Yes — **SQL has a well-defined _logical_ order of execution**, and that order applies **regardless of whether you write the query as a single block or using subqueries**.
> 
> What changes with subqueries is **scope and visibility**, not the fundamental execution phases.
> 
> Let’s make this precise.
> 
> ---
> 
> ## 1. Logical Order of Execution (Canonical Model)
> 
> For a single `SELECT` query, PostgreSQL (and SQL in general) follows this **logical** order:
> 
> 1. **FROM**
>     
> 2. **JOIN / ON**
>     
> 3. **WHERE**
>     
> 4. **GROUP BY**
>     
> 5. **HAVING**
>     
> 6. **SELECT**
>     
> 7. **WINDOW FUNCTIONS**
>     
> 8. **ORDER BY**
>     
> 9. **LIMIT / OFFSET**
>     
> 
> This is _not_ textual order. It is the semantic evaluation order.
> 
> ---
> 
> ## 2. Where Subqueries Fit In
> 
> A subquery is **not executed “first” just because it is nested**.
> 
> Instead:
> 
> - A subquery is evaluated **when its result is needed**
>     
> - It has its **own independent logical execution order**
>     
> - The outer query cannot see inside the subquery except for its output columns
>     
> 
> Each query block follows the same rules.
> 
> ---
> 
> ## 3. Example: Derived Table (FROM Subquery)
> 
> ```sql
> SELECT dept_code, rank
> FROM (
>     SELECT dept_code,
>            RANK() OVER (ORDER BY COUNT(*) DESC) AS rank
>     FROM departments d
>     LEFT JOIN empsalary e ON ...
>     GROUP BY dept_code
> ) t;
> ```
> 
> ### Execution flow
> 
> 1. Inner query executes fully:
>     
>     - FROM → JOIN → GROUP BY → SELECT → WINDOW
>         
> 2. Its result becomes a **virtual table**
>     
> 3. Outer query runs **its own** execution order
>     
> 
> The inner query does _not_ “interleave” with the outer one.
> 
> ---
> 
> ## 4. Correlated Subqueries (Important Distinction)
> 
> Now consider:
> 
> ```sql
> SELECT d.dept_code,
>        (
>          SELECT COUNT(*)
>          FROM empsalary e
>          WHERE e.depname = d.dept_code
>        )
> FROM departments d;
> ```
> 
> Here:
> 
> - The subquery **depends on each row** of the outer query
>     
> - Logically:
>     
>     1. Outer `FROM departments` produces a row
>         
>     2. Subquery is evaluated **per row**
>         
> - Physically, the planner may optimize this into a join — but logically it is still per-row
>     
> 
> Key rule:
> 
> > Correlation affects _when_ a subquery is evaluated, not _whether_ SQL has an execution order.
> 
> ---
> 
> ## 5. Why SQL Needs This Order
> 
> Without a strict order:
> 
> - `COUNT()` inside `RANK()` would be undefined
>     
> - `WHERE` could not filter before aggregation
>     
> - Window functions would be ambiguous
>     
> 
> This is why SQL **forbids** certain things:
> 
> - Window functions in `WHERE`
>     
> - Aggregates in `WHERE`
>     
> - Referencing SELECT aliases in `WHERE`
>     
> 
> They would violate the execution order.
> 
> ---
> 
> ## 6. Logical vs Physical Execution (Critical Distinction)
> 
> What you are learning is the **logical** order.
> 
> PostgreSQL may physically:
> 
> - Reorder joins
>     
> - Push filters down
>     
> - Inline subqueries
>     
> - Replace correlated subqueries with joins
>     
> 
> But it must produce a result **as if** the logical order was followed.
> 
> This is called **relational equivalence**.
> 
> ---
> 
> ## 7. Mental Model to Keep
> 
> Think in terms of **query blocks**:
> 
> - Each `SELECT` defines a boundary
>     
> - Inside each boundary:
>     
>     ```
>     FROM → WHERE → GROUP BY → SELECT → WINDOW → ORDER
>     ```
>     
> - Subqueries do not break this model — they replicate it
>     
> 
> ---
> 
> ## 8. One-Sentence Answer
> 
> > Yes — SQL has a strict logical order of execution, and every subquery follows that same order independently; nesting changes scope, not the execution semantics.
> 
> If you want, next we can:
> 
> - Map this order to **why certain syntax is illegal**
>     
> - Trace a **correlated subquery vs join** side by side
>     
> - Show how PostgreSQL rewrites queries internally
>     
> 
> Just tell me which direction you want.

### Advanced Join Scenarios
[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Joins\|SQL questions#Joins]]
[[Learning/Programming/Python/Practice/Interview questions/BOA/Q&A/SQL questions#Tables\|tables]]

```quiz
type: radio
content: |
    What will this query return?
    ```
    SELECT d.dept_code, 
           COUNT(e.empno) as employee_count,
           STRING_AGG(e.empno::text, ', ' ORDER BY e.empno) as employee_list
    FROM departments d
    LEFT JOIN empsalary e ON d.dept_code = e.depname
    GROUP BY d.dept_code
    ORDER BY employee_count DESC;
    ```

options:
- content: |
    A list of departments with the count of employees and a comma-separated list of employee numbers
  feedback: Correct! This aggregates department data, showing employee counts and lists for each department.
  correct: true

- content: |
    A list of all employees with their department codes
  feedback: No, this query aggregates by department, not by employee.

- content: |
    Only departments that have employees
  feedback: No, LEFT JOIN includes all departments, even those with no employees (which will show 0 count).

- content: |
    An error because STRING_AGG can't be used with window functions
  feedback: STRING_AGG is an aggregate function, not a window function, so it works fine with GROUP BY.
```


> [!question]- what is `STRING_AGG(e.empno::text, ', ' ORDER BY e.empno)`
> 
> `STRING_AGG(e.empno::text, ', ' ORDER BY e.empno)` is a **PostgreSQL aggregate function call** that:
> 
> > **Concatenates multiple row values into a single ordered string, with a specified delimiter.**
> 
> Let’s decompose it precisely.
> 
> ---
> 
> ## 1. `STRING_AGG(...)` — What It Is
> 
> `STRING_AGG` is a **group aggregate function**.
> 
> Signature (simplified):
> 
> ```sql
> STRING_AGG(expression, delimiter [ORDER BY expression])
> ```
> 
> It operates **after `GROUP BY`**, exactly like `COUNT`, `SUM`, etc.
> 
> ---
> 
> ## 2. `e.empno::text` — Why the Cast
> 
> ```sql
> e.empno::text
> ```
> 
> - `empno` is an integer
>     
> - `STRING_AGG` works on text values
>     
> - `::text` is PostgreSQL’s cast operator
>     
> 
> Equivalent forms:
> 
> ```sql
> CAST(e.empno AS text)
> ```
> 
> ---
> 
> ## 3. `', '` — The Delimiter
> 
> ```sql
> ', '
> ```
> 
> This is inserted **between** values:
> 
> ```
> 11, 1, 2
> ```
> 
> (not after the last element)
> 
> ---
> 
> ## 4. `ORDER BY e.empno` — Why It Matters
> 
> ```sql
> STRING_AGG(... ORDER BY e.empno)
> ```
> 
> Without `ORDER BY`:
> 
> - Concatenation order is **undefined**
>     
> - Depends on execution plan
>     
> 
> With `ORDER BY`:
> 
> - PostgreSQL sorts values **within each group**
>     
> - Guarantees deterministic output
>     
> 
> Example for `sales`:
> 
> ```
> 1, 2, 11
> ```
> 
> not
> 
> ```
> 11, 1, 2
> ```
> 
> ---
> 
> ## 5. Where It Executes in the Logical Order
> 
> Inside a grouped query:
> 
> 1. `FROM / JOIN`
>     
> 2. `WHERE`
>     
> 3. `GROUP BY`
>     
> 4. **Aggregate functions**
>     
>     - `COUNT(e.empno)`
>         
>     - `STRING_AGG(...)`
>         
> 5. `SELECT`
>     
> 6. `WINDOW`
>     
> 7. `ORDER BY`
>     
> 
> So `STRING_AGG` runs **once per group**, not per row.
> 
> ---
> 
> ## 6. Concrete Example
> 
> ```sql
> SELECT
>     d.dept_code,
>     COUNT(e.empno) AS emp_count,
>     STRING_AGG(e.empno::text, ', ' ORDER BY e.empno) AS emp_list
> FROM departments d
> LEFT JOIN empsalary e ON d.dept_code = e.depname
> GROUP BY d.dept_code;
> ```
> 
> Result:
> 
> |dept_code|emp_count|emp_list|
> |---|---|---|
> |sales|3|1, 2, 11|
> |IT|3|3, 4, 5|
> |support|2|6, 7|
> |hr|0|NULL|
> 
> Notes:
> 
> - `hr` → no rows → `STRING_AGG` returns `NULL`
>     
> - `COUNT` returns `0`
>     
> 
> ---
> 
> ## 7. Why This Is an Aggregate, Not a Window Function
> 
> Common confusion:
> 
> ```sql
> STRING_AGG(...) OVER (...)
> ```
> 
> This **would** be a window function (allowed in PostgreSQL 14+ with restrictions).
> 
> Your version **without `OVER()`**:
> 
> - Collapses rows
>     
> - Produces one value per group
>     
> 
> ---
> 
> ## 8. Mental Model
> 
> Think of `STRING_AGG` as:
> 
> > “Take all the values in this group, sort them, convert to text, then glue them together with commas.”
> 
> ---
> 
> ## 9. When This Is Typically Used
> 
> - Listing child rows per parent
>     
> - Debugging grouped data
>     
> - Reporting / human-readable output
>     
> - Avoiding application-side loops
>     
> 
> ---
> 
> ### One-line takeaway
> 
> `STRING_AGG(e.empno::text, ', ' ORDER BY e.empno)` concatenates employee numbers **within each group**, in sorted order, into a single comma-separated string.
> 
> If you want, next we can:
> 
> - Compare `STRING_AGG` with `ARRAY_AGG`
>     
> - Show how to handle `NULL`s explicitly
>     
> - Convert this into a window version
>     
> 
> Just say the word.

> [!Multi-Column] 
> > [!g-white|wide-1]- empsalary
> > | **depname** | **empno** | **salary** |
> > | ----------- | --------- | ---------- |
> > | sales       | 11        | 5200       |
> > | sales       | 1         | 5000       |
> > | sales       | 2         | 4800       |
> > | IT          | 5         | 8000       |
> > | IT          | 4         | 7700       |
> > | IT          | 3         | 6000       |
> > | support     | 7         | 4200       |
> > | support     | 6         | 4100       |
> 
> > [!g-white|wide-2]- departments
> > | **dept_code** | **dept_name**          | **manager** | **location** |
> > | ------------- | ---------------------- | ----------- | ------------ |
> > | sales         | Sales & Marketing      | Sarah Jain  | Chennai      |
> > | IT            | Information Technology | Raj Patel   | Bangalore    |
> > | support       | Customer Support       | Priya Menon | Hyderabad    |
> > | hr            | Human Resources        | Anil Kumar  | Mumbai       |

```quiz
type: text
content: |
    Write a query that shows for each employee: 
    1. Their details (empno, salary)
    2. Their department's average salary
    3. How much their salary differs from their department average
    4. Their rank within their department by salary (highest salary = rank 1)

    Use both the empsalary and departments tables to include department names.

correct: |
    SELECT 
        d.dept_name,
        e.empno,
        e.salary,
        AVG(e.salary) OVER (PARTITION BY e.depname) as dept_avg_salary,
        e.salary - AVG(e.salary) OVER (PARTITION BY e.depname) as diff_from_avg,
        RANK() OVER (PARTITION BY e.depname ORDER BY e.salary DESC) as dept_rank
    FROM empsalary e
    INNER JOIN departments d ON e.depname = d.dept_code
    ORDER BY d.dept_name, dept_rank;
```



# Testing Area

You can test your queries here:

```bash
## Write and test your SQL here
psql -c "

"
```



# Coding Practice



## 1. Basic Queries & Constraints
**Scenario:** You're creating a new `projects` table with these requirements:
- Each project must have a unique ID, name, start date, and budget
- Budget must be positive and less than 1,000,000
- Status can only be 'planned', 'active', or 'completed'
- Start date must be after 2020-01-01

```bash
## Write and test your SQL here
psql -c "
-- Create the projects table with appropriate constraints
"
```

## 2. Window Functions Challenge
**Task:** For each department in `empsalary`, find:
1. The employee with the highest salary
2. The employee with the lowest salary
3. The difference between each employee's salary and their department average
4. A cumulative salary total within each department (ordered by empno)

```bash
## Write and test your SQL here
psql -c "

"
```

## 3. Complex CTE & Join
**Problem:** Create a report showing:
- Department name, manager, and location from `departments`
- Number of employees and average salary from `empsalary`
- The highest paid employee in each department
- Only include departments where average salary > 5000

*Hint: You'll need multiple CTEs and joins*

```bash
## Write and test your SQL here
psql -c "

"
```

## 4. Indexing Performance
**Scenario:** The following query is running slowly:
```sql
SELECT * FROM empsalary 
WHERE depname = 'IT' AND salary > 6000 
ORDER BY empno;
```

1. Write the CREATE INDEX statement(s) to optimize this query
2. Write a query to check if your index is being used

```bash
## Write and test your SQL here
psql -c "
-- Create your index(es) here
"

psql -c "
-- Check if index is being used
"
```

## 5. Subquery vs Join Transformation
**Task:** You have this subquery:
```sql
SELECT d.dept_name, d.manager
FROM departments d
WHERE d.dept_code IN (
    SELECT depname 
    FROM empsalary 
    GROUP BY depname 
    HAVING AVG(salary) > 5500
);
```

1. Rewrite it using a JOIN instead of a subquery
2. Rewrite it using a CTE
3. Which version is most readable? Why?

```bash
## Write and test your SQL here
psql -c "
-- JOIN version
"

psql -c "
-- CTE version
"
```

## 6. Temporary Table & Data Transformation
**Scenario:** You need to:
1. Create a temporary table containing employees earning above their department average
2. Add a column to categorize them as 'High Earner'
3. Join this with department details
4. Export only IT and Sales department results

```bash
## Write and test your SQL here
psql -c "

"
```

## 7. CRUD Operations with Constraints
**Task:** Perform these operations on a new `employee_bonus` table:
1. Create table with: employee_id (references empsalary.empno), bonus_amount (positive), bonus_date
2. Insert bonuses for employees 1, 3, 5, 11
3. Update bonus for employee 5 to be 15% higher
4. Delete bonuses less than 1000
5. Try to insert a bonus for non-existent employee 99 (should fail)

```bash
## Write and test your SQL here
psql -c "

"
```

## 8. Advanced Window Functions
**Challenge:** For the `empsalary` table:
1. Assign quartiles (4 equal groups) within each department based on salary
2. Show running percentage of total department salary
3. For each employee, show the next higher salary in their department
4. Create a "salary band" report showing how many employees fall into 1000-unit salary bands

```bash
## Write and test your SQL here
psql -c "

"
```

## 9. View & Stored Procedure
**Requirements:**
1. Create a view `department_summary` showing dept_code, employee_count, total_salary, avg_salary
2. Create a stored procedure `give_raise(dept_code, percentage)` that updates all employees in that department
3. Create a function `get_department_stats(dept_code)` that returns the summary for one department

```bash
## Write and test your SQL here
psql -c "

"
```

## 10. Complex Mapping Challenge
**Scenario:** You have a third table `salary_grades`:
```
grade | min_salary | max_salary
A     | 8000       | 10000
B     | 6000       | 7999
C     | 4000       | 5999
D     | 0          | 3999
```

**Task:** 
1. Create and populate this table
2. Map each employee to their salary grade
3. Show department-wise grade distribution
4. Find departments where no employee has grade 'A'

```bash
## Write and test your SQL here
psql -c "

"
```

**Tips for Practice:**
- Test each query before moving to the next
- Use `EXPLAIN ANALYZE` to understand query performance
- Try to write multiple solutions for the same problem
- Add comments explaining your approach

When you're ready, I can provide the solutions or help debug your queries!

