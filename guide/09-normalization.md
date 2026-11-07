# 9. Logical design and normalization

**Time:** 6 minutes

> [!TIP]
> **TL;DR**
> - Good primary keys are **stable, simple, meaningless**.
> - Many-to-many → a **new table** with two foreign keys.
> - **BCNF** = whenever any column depends on B, B is unique. The gold standard.

## Turning the ER model into tables

| ER element | Becomes |
| --- | --- |
| Entity | Table with a primary key |
| One-to-many | Foreign key on the **many** side |
| One-to-one | Foreign key on one side (usually the table with fewer rows) |
| Many-to-many | **New table**: two foreign keys = composite primary key |
| Plural attribute | New table with a foreign key back |
| Required attribute | NOT NULL |
| Unique attribute | UNIQUE |

## Keys

- **Stable** (doesn't change), **simple** (small, easy to type), **meaningless** (no descriptive info).
- **Artificial key:** designer-made, usually an auto-generated integer. Ticks all three boxes.
- **Candidate key:** unique **and minimal**. The designer picks one as the primary key.
- **Non-key column:** not part of any candidate key.

## Dependence

- **Functional dependence:** A depends on B if each B value maps to at most one A value (B → A).
- **Redundancy:** related values repeated in a table. Normal forms reduce it.
- **Trivial dependency:** A's columns are a subset of B's, so A always depends on B.

## The normal forms

| Form | Rule | Plain English |
| --- | --- | --- |
| **1NF** | One value per cell, has a primary key, non-key columns depend on it | No lists in a cell |
| **2NF** | 1NF + non-key columns depend on the **whole** key | Nothing hangs off half a composite key |
| **3NF** | Non-key A depends on B → B is unique | No non-key → non-key dependence |
| **BCNF** | **Any** A depends on B → B is unique | 3NF with "non-key" removed |

**Example:** `Employee(ID, Name, DeptCode, DeptName)` breaks 3NF. DeptName depends on DeptCode, which repeats. Fix: move it to `Department(DeptCode, DeptName)`.

- **Normalization:** split tables into higher normal forms. **Last step of logical design.**
- **Denormalization:** merge tables on purpose, adding redundancy (usually for faster reads).
- BCNF is ideal for tables with frequent inserts, updates, and deletes.

> [!WARNING]
> **Exam traps**
> - In 3NF/BCNF, B must be **unique**, not necessarily minimal, so B isn't always a candidate key.
> - A candidate key must be **minimal**; "unique" alone isn't enough.

## Quick check

<details><summary>1. How do you implement a many-to-many relationship?</summary>

**A new table holding foreign keys to both tables.**
</details>

<details><summary>2. Three properties of a good primary key?</summary>

**Stable, simple, meaningless.**
</details>

<details><summary>3. Which form drops the word "non-key" from 3NF?</summary>

**BCNF.**
</details>

[← Back](08-design-and-er-modeling.md) · [Next: Physical design →](10-physical-design.md)
