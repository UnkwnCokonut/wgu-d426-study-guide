# 7. Joins, subqueries, and views

**Time:** 5 minutes

**Exam weight:** Competency 2, Determines SQL Queries (30% of the exam)

> [!TIP]
> **TL;DR**
> - The join type decides what happens to **unmatched** rows.
> - **LEFT** keeps all left rows; **RIGHT** keeps all right rows; **FULL** keeps everything.
> - A **materialized view** stores its data and must be refreshed.

## Which rows survive?

| Join | Keeps | Unmatched side shows |
| --- | --- | --- |
| INNER | Only matches | Dropped |
| LEFT | All left + matching right | NULL in right columns |
| RIGHT | All right + matching left | NULL in left columns |
| FULL | Everything from both | NULL wherever no match |
| CROSS | Every combination; **no ON clause** | n/a |

```sql
SELECT E.Name, D.Name AS Department
FROM Employee AS E
LEFT JOIN Department AS D ON E.DeptCode = D.Code;
```

## More join words

- **Outer join** = LEFT, RIGHT, or FULL (anything that keeps unmatched rows).
- **Equijoin** uses `=`. **Non-equijoin** uses `<`, `>`, and so on.
- **Self-join:** a table joined to itself (employee → manager). Use aliases.
- **UNION** stacks two SELECT results into one. MySQL has no FULL JOIN, so you do LEFT JOIN UNION RIGHT JOIN.

## Subqueries

A query inside a query. Also called a **nested** or **inner** query.

```sql
SELECT Name FROM Employee
WHERE Salary > (SELECT AVG(Salary) FROM Employee);
```

## Views

- **View:** a table defined by a SELECT. The tables it reads are its **base tables**.
- **Materialized view:** stores its data; must be **refreshed** when base tables change.
- **WITH CHECK OPTION:** rejects inserts/updates through the view that don't match the view's WHERE.

> [!WARNING]
> **Exam traps**
> - CROSS JOIN has **no ON clause**.
> - "Outer join" never means INNER.

## Quick check

<details><summary>1. You need every employee, even ones with no department. Which join (Employee on the left)?</summary>

**LEFT JOIN.**
</details>

<details><summary>2. What do you call a join of a table to itself?</summary>

**Self-join.**
</details>

<details><summary>3. Which view type must be refreshed?</summary>

**Materialized view.**
</details>

[← Back](06-writing-queries.md) · [Next: Design and ER modeling →](08-design-and-er-modeling.md)
