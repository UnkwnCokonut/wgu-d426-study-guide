# 6. Writing queries

**Time:** 5 minutes

**Exam weight:** Competency 2, Determines SQL Queries (30% of the exam)

> [!TIP]
> **TL;DR**
> - Clause order: **SELECT → FROM → WHERE → GROUP BY → HAVING → ORDER BY**.
> - **WHERE** filters rows; **HAVING** filters groups.
> - LIKE: `%` = any number of characters, `_` = exactly one.

## The whole thing in one query

```sql
SELECT   DeptCode, COUNT(*) AS Headcount, AVG(Salary) AS AvgPay
FROM     Employee
WHERE    Salary > 30000          -- 1. filter ROWS
GROUP BY DeptCode                -- 2. one group per department
HAVING   COUNT(*) >= 5           -- 3. filter GROUPS
ORDER BY Headcount DESC;         -- 4. sort what's left
```

Mnemonic: **S**weaty **F**eet **W**ill **G**ive **H**orrible **O**dors.

## Filtering

| Operator | Meaning | Example |
| --- | --- | --- |
| BETWEEN | Inclusive range | `Age BETWEEN 18 AND 30` = `>= 18 AND <= 30` |
| IN | Any value in a list | `State IN ('PA', 'NJ')` |
| LIKE `%` | Any number of characters (even zero) | `'L%t'` → Lt, Lot, Lift |
| LIKE `_` | Exactly one character | `'L_t'` → Lot, Lit (not Lt, Loot) |
| IS NULL | Tests for NULL | `= NULL` never matches |

## Sorting and naming

- **ORDER BY** sorts ascending by default. Add **DESC** for descending.
- **Alias:** a temporary name with optional **AS**: `Salary AS Pay`.

## Functions

| Function | Example → result |
| --- | --- |
| ABS(n) | `ABS(-5)` → 5 |
| LOWER(s) | `LOWER('MySQL')` → 'mysql' |
| TRIM(s) | `TRIM('  test  ')` → 'test' |
| HOUR / MINUTE / SECOND | `HOUR('22:11:45')` → 22 |
| UPPER(s) | `UPPER('sql')` → 'SQL' |
| CONCAT(s1, s2, ...) | `CONCAT('Data', 'base')` → 'Database' |
| SUBSTRING(s, pos, len) | `SUBSTRING('Database', 1, 4)` → 'Data' |
| REPLACE(s, from, to) | `REPLACE('cats and dogs', 'and', 'or')` → 'cats or dogs' |

## Aggregates

**COUNT, MIN, MAX, SUM, AVG** turn many rows into one value.

- They only see rows that pass WHERE.
- With GROUP BY, they compute once per group.
- They skip NULLs; `COUNT(*)` still counts every row.

> [!WARNING]
> **Exam traps**
> - Filtering on an aggregate (`COUNT(*) > 5`) needs **HAVING**, not WHERE.
> - BETWEEN **includes** both ends.

## Quick check

<details><summary>1. Which clause comes right after GROUP BY?</summary>

**HAVING.**
</details>

<details><summary>2. Does LIKE 'L_t' match "Loot"?</summary>

**No.** `_` is exactly one character.
</details>

<details><summary>3. AVG skips which values?</summary>

**NULLs.**
</details>

[← Back](05-keys-and-constraints.md) · [Next: Joins, subqueries, views →](07-joins-subqueries-views.md)
