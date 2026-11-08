# 4. Core statements

**Time:** 4 minutes

**Exam weight:** Competency 1, Explains Database Attributes and SQL Commands (28% of the exam)

> [!TIP]
> **TL;DR**
> - **DELETE** = chosen rows · **TRUNCATE** = all rows · **DROP** = the whole table.
> - UPDATE or DELETE **without WHERE** changes every row.
> - **MERGE** copies from a **source** table into a **target** table.

## What each one does

| Statement | Does | Watch for |
| --- | --- | --- |
| CREATE TABLE | Makes a table: name, columns, data types | Constraints go here too |
| DROP TABLE | Deletes the table **and** its rows | Structure is gone |
| ALTER TABLE | ADD, DROP, or CHANGE columns | Also adds/drops constraints |
| INSERT | Adds rows | Skip values for auto-increment keys |
| UPDATE | Changes rows with SET | No WHERE = every row |
| DELETE | Removes rows | No WHERE = every row |
| TRUNCATE | Removes all rows, keeps the table | ≈ DELETE with no WHERE |
| MERGE | Source → target | |

## See them in action

```sql
CREATE TABLE Employee (
  ID        INT AUTO_INCREMENT,
  Name      VARCHAR(60) NOT NULL,
  Salary    DECIMAL(8, 2),
  HireDate  DATE,
  DeptCode  INT,
  PRIMARY KEY (ID),
  FOREIGN KEY (DeptCode) REFERENCES Department(Code) ON DELETE SET NULL
);

INSERT INTO Employee (Name, Salary, HireDate) VALUES ('Sam Snead', 35000.00, '2026-01-15');
UPDATE Employee SET Salary = 40000 WHERE ID = 1;
DELETE FROM Employee WHERE ID = 1;
ALTER TABLE Employee ADD Phone VARCHAR(15);
DROP TABLE Employee;
```

A syntax error in the MySQL Command-Line Client returns an **error code and description**.

> [!WARNING]
> **Exam traps**
> - DROP removes the table itself; TRUNCATE leaves an empty table.
> - The INSERT above skips `ID` on purpose: it's auto-increment.

## Quick check

<details><summary>1. UPDATE Employee SET Salary = 0; — what happens?</summary>

**Every row's salary becomes 0.** No WHERE clause.
</details>

<details><summary>2. Which statement removes all rows but keeps the table?</summary>

**TRUNCATE.**
</details>

<details><summary>3. Which clause does ALTER TABLE use to rename/modify a column?</summary>

**CHANGE** (alongside ADD and DROP).
</details>

[← Back](03-sql-language-and-types.md) · [Next: Keys and constraints →](05-keys-and-constraints.md)
