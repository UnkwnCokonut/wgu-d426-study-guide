# 3. SQL language and data types

**Time:** 5 minutes

**Exam weight:** Competency 1, Explains Database Attributes and SQL Commands (28% of the exam)

> [!TIP]
> **TL;DR**
> - Five sublanguages: **DDL** (structure), **DQL** (SELECT), **DML** (change data), **DCL** (access), **DTL** (transactions).
> - **DECIMAL(M, D)** = M total digits, D after the decimal.
> - Integer sizes: TINYINT 1 byte · SMALLINT 2 · MEDIUMINT 3 · INT 4 · BIGINT 8.

## The five sublanguages

| Sublanguage | Job | Statements |
| --- | --- | --- |
| **DDL** Data Definition | Defines structure | CREATE, ALTER, DROP |
| **DQL** Data Query | Retrieves data | SELECT |
| **DML** Data Manipulation | Changes data | INSERT, UPDATE, DELETE |
| **DCL** Data Control | Controls access | GRANT, REVOKE |
| **DTL** Data Transaction | Manages transactions | COMMIT, ROLLBACK |

## Parts of a statement

| Type | Examples |
| --- | --- |
| **Literal** (explicit value) | `'String'`, `"String"`, `123`, `x'0fa2'` |
| **Keyword** (special meaning) | `SELECT`, `FROM`, `WHERE` |
| **Identifier** (object name) | `City`, `Name`, `Population` |
| **Expression** (evaluates to one value) | `Population > 1000000 OR Name = 'Tokyo'` |
| **Comment** (ignored) | `-- one line`, `/* many lines */` |

## Data types

| Type | Stores | Example |
| --- | --- | --- |
| INT / INTEGER | Whole numbers, 4 bytes | 34, -739448 |
| DECIMAL(M, D) | M digits total, D after the point | DECIMAL(5, 2) → 999.99 max |
| VARCHAR(N) | Text, 0 to N characters | 'Seattle' |
| CHAR(N) | Text, fixed length N | 'PA' in CHAR(2) |
| DATE | Year, month, day | '2026-11-08' |

| Integer | Bytes | Signed | Unsigned |
| --- | --- | --- | --- |
| TINYINT | 1 | -128 to 127 | 0 to 255 |
| SMALLINT | 2 | -32,768 to 32,767 | 0 to 65,535 |
| MEDIUMINT | 3 | -8,388,608 to 8,388,607 | 0 to 16,777,215 |
| INT | 4 | about ±2.1 billion | 0 to 4,294,967,295 |
| BIGINT | 8 | -2^63 to 2^63 - 1 | 0 to 2^64 - 1 |

## Operators worth remembering

- `%` modulo = remainder: `5 % 2` → `1`
- `^` = power in the course table: `5^2` → `25`
- `'2019-08-13' > '2021-08-13'` → FALSE (dates compare in order)

> [!WARNING]
> **Exam traps**
> - SELECT is **DQL**, not DML. (Some study sheets lump it into DML; the five-sublanguage model doesn't.)
> - DECIMAL(5, 2) is **5 total** digits, not 5 before the decimal.
> - Real MySQL treats `^` as XOR, but answer with the course table.

## Quick check

<details><summary>1. GRANT belongs to which sublanguage?</summary>

**DCL.**
</details>

<details><summary>2. How many bytes is SMALLINT?</summary>

**2.**
</details>

<details><summary>3. Largest value DECIMAL(5, 2) can hold?</summary>

**999.99.**
</details>

[← Back](02-relational-model.md) · [Next: Core statements →](04-core-statements.md)
