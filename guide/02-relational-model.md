# 2. Relational model

**Time:** 3 minutes

**Exam weight:** Competency 1, Explains Database Attributes and SQL Commands (28% of the exam)

> [!TIP]
> **TL;DR**
> - A table = a name + a fixed sequence of columns + a varying **set** of rows.
> - Rows have **no order** (it's a set). Tuples **do** have order.
> - **Data independence:** how data is stored never changes query results.

## The building blocks

- A table needs **at least one column**, but can have **zero rows** (an **empty table**).
- **Column:** has a name and a data type.
- **Row:** an unnamed tuple of values, one per column.
- **Cell:** one column of one row.
- **Tuple:** ordered, so (a, b, c) ≠ (c, b, a).
- **Data type:** a named set of values that column values come from.

## Same thing, three names

| Relational | SQL | Old file term |
| --- | --- | --- |
| Relation | Table | File |
| Tuple | Row | Record |
| Attribute | Column | Field |

## Relational algebra, the three to know

| Operation | Does | SQL feel |
| --- | --- | --- |
| **Select** | Picks **rows** | `WHERE` |
| **Project** | Picks **columns** | `SELECT Col1, Col2` |
| **Product** | Every row × every row (Table1 × Table2) | `CROSS JOIN` |

Trick: **P**roject = **P**illars (columns stand up).

## Two kinds of rules

- **Relational (structural) rules** apply to every relational database: unique primary key, unique column names, no duplicate rows.
- **Business rules** come from business policy and apply to one database: "a course in a registration must exist in the catalog."

> [!WARNING]
> **Exam traps**
> - "Attribute" = column, not row.
> - A table with no rows is still valid.

## Quick check

<details><summary>1. A row is also called a…?</summary>

**Tuple** (or record).
</details>

<details><summary>2. Why do rows have no inherent order?</summary>

**A table is a set of rows**, and sets are unordered.
</details>

<details><summary>3. What principle says physical storage changes never change results?</summary>

**Data independence.**
</details>

[← Back](01-database-basics.md) · [Next: SQL language →](03-sql-language-and-types.md)
