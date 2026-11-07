# 10. Physical design

**Time:** 5 minutes

> [!TIP]
> **TL;DR**
> - **Heap** = fast inserts · **sorted** = fast ranges · **hash** = fast exact matches · **cluster** = fast joins.
> - **High hit ratio → table scan. Low hit ratio → index scan.**
> - **Dense** index = entry per row. **Sparse** = entry per block.

## Table structures

| Structure | Rows stored | Best for | Weak at |
| --- | --- | --- | --- |
| **Heap** | No order | Inserts, bulk loads | Searching |
| **Sorted** | By a sort column | Range queries, ORDER BY | Inserts |
| **Hash** | In buckets by hash key | Exact-match lookups | Ranges |
| **Table cluster** | Rows of 2+ tables interleaved | Joins on the cluster key | Scanning one table |

**Modulo hash:** key ÷ number of buckets, remainder = bucket. Key 46 with 10 buckets → bucket 6.

## Scans

- **Table scan:** reads table blocks directly, no index.
- **Index scan:** reads the index to find which table blocks to read.
- **Hit ratio** (filter factor, selectivity): % of rows the query selects.
- **Binary search:** split the sorted index in half until you find it.

## Index types

| Index | Idea |
| --- | --- |
| Dense | Entry for every **row** |
| Sparse | Entry for every **block** (table sorted on the column) |
| Hash | Entries in buckets |
| Bitmap | Grid of 1s and 0s; great for few distinct values |
| Logical | Stores primary key values, not block pointers |
| Function | Indexes `f(column)`, like `UPPER(Name)` |
| Multi-level | An index on an index |

```sql
CREATE INDEX IdxEmpName ON Employee (Name);
```

## Storage

- **Tablespace:** maps one or more tables to a single file (`CREATE TABLESPACE`).
- **Partition:** a subset of a table. **Horizontal** splits rows; **vertical** splits columns.
- **Storage engine:** does the low-level reads/writes. MySQL default: **InnoDB**.

> [!WARNING]
> **Exam traps**
> - Indexes help **low** hit ratio queries. Selecting most rows? A table scan wins.
> - Physical design never changes **results**.

## Quick check

<details><summary>1. Fastest structure for bulk loading?</summary>

**Heap table.**
</details>

<details><summary>2. A query returns 90% of rows. Table scan or index scan?</summary>

**Table scan.**
</details>

<details><summary>3. Which object maps tables to a single file?</summary>

**Tablespace.**
</details>

[← Back](09-normalization.md) · [Back to the cram sheet →](00-cram-sheet.md)
