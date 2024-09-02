# Products Table Documentation

## Description

This table stores information about products, including their identification, fat content, and recyclability.

## Table: Products

### Columns

| Column Name  | Data Type         | Description                                                      |
|--------------|-------------------|------------------------------------------------------------------|
| `product_id` | `INT`             | Unique identifier for each product.                              |
| `low_fats`   | `ENUM('Y', 'N')`  | Indicates whether the product is low in fat (`Y`) or not (`N`).  |
| `recyclable` | `ENUM('Y', 'N')`  | Indicates whether the product is recyclable (`Y`) or not (`N`).  |

## Example

### Input

**Products table:**

| product_id | low_fats | recyclable |
|------------|----------|------------|
| 0          | Y        | N          |
| 1          | Y        | Y          |
| 2          | N        | Y          |
| 3          | Y        | Y          |
| 4          | N        | N          |

### Output

| product_id |
|------------|
| 1          |
| 3          |

### Explanation

Only products with `product_id` 1 and 3 are both low in fat (`Y`) and recyclable (`Y`).

### SQL Query

``` SQL
-- Write your PostgreSQL query statement below
select p.product_id
from
Products p
where
low_fats = 'Y'
AND
recyclable = 'Y'
```
