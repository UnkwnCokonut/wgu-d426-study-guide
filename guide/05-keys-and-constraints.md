# 5. Keys and constraints

**Time:** 5 minutes

> [!TIP]
> **TL;DR**
> - **Primary key** identifies each row: unique and not NULL.
> - **Foreign key** points at a primary key: same data type, name can differ.
> - Four fix-ups for broken references: **RESTRICT, SET NULL, SET DEFAULT, CASCADE**.

## Primary keys

- **Simple** = one column. **Composite** = several columns.
- **Auto-increment column:** gets the next number automatically on insert.
- Two classic insert mistakes:
  1. Supplying a value for an auto-increment key.
  2. Leaving out the value for a key that is *not* auto-increment.

## Foreign keys and referential integrity

- Declared with `FOREIGN KEY (...) REFERENCES Table(...)`.
- **Referential integrity:** every foreign key value matches an existing primary key, or is NULL.

| Action | When a change would break a reference… |
| --- | --- |
| **RESTRICT** | Reject the change |
| **SET NULL** | Set the broken foreign keys to NULL |
| **SET DEFAULT** | Set them to the column's default value |
| **CASCADE** | Carry the change through (ON DELETE CASCADE deletes the child rows) |

```sql
FOREIGN KEY (DeptCode) REFERENCES Department(Code)
  ON DELETE CASCADE
  ON UPDATE SET NULL
```

## Constraints

A **constraint** is a rule on allowed values. Break it and the statement is rejected.

| Constraint | Rule |
| --- | --- |
| NOT NULL | Can't be empty |
| UNIQUE | No duplicates |
| PRIMARY KEY | Unique + not NULL |
| FOREIGN KEY | Must match a referenced key |
| CHECK | Must pass a condition: `CHECK (Salary > 0)` |
| DEFAULT | Value used when none is given |

- **Column constraint:** written right after one column's definition.
- **Table constraint:** its own clause; can cover several columns, like `PRIMARY KEY (A, B)`.
- Change them later with `ALTER TABLE ... ADD / DROP / CHANGE`.

> [!WARNING]
> **Exam traps**
> - Foreign key and primary key **names may differ**; **types must match**.
> - CASCADE *propagates*. RESTRICT *rejects*. Don't swap them.

## Quick check

<details><summary>1. Deleting a department should delete its employees too. Which action?</summary>

**ON DELETE CASCADE.**
</details>

<details><summary>2. Which constraint enforces "Salary must be positive"?</summary>

**CHECK (Salary > 0).**
</details>

<details><summary>3. Primary key made of two columns?</summary>

**Composite primary key.**
</details>

[← Back](04-core-statements.md) · [Next: Writing queries →](06-writing-queries.md)
