# Cram sheet

**Time:** 3 minutes. Read this right before the exam.

## The 10 facts

1. **Clause order:** SELECT → FROM → WHERE → GROUP BY → HAVING → ORDER BY. *Sweaty Feet Will Give Horrible Odors.*
2. **WHERE vs HAVING:** WHERE filters rows before grouping. HAVING filters groups after GROUP BY.
3. **Design phases:** Analysis (ER model) → Logical design (tables, keys, normalization) → Physical design (indexes, storage).
4. **Data independence:** physical design changes speed, never query results.
5. **Foreign key:** refers to a primary key. Data types must match; names can differ.
6. **Referential integrity actions:** RESTRICT rejects · SET NULL · SET DEFAULT · CASCADE propagates.
7. **Joins:** INNER = matches only · LEFT = all left · RIGHT = all right · FULL = all of both · CROSS = every combination, no ON.
8. **3NF vs BCNF:** 3NF says a *non-key* column may depend only on a unique column. BCNF says *any* column. BCNF is the gold standard.
9. **Sublanguages:** DDL structure · DQL SELECT · DML change data · DCL access · DTL transactions.
10. **Danger zone:** UPDATE or DELETE with no WHERE hits every row.

## Don't mix these up

| Pair | Difference |
| --- | --- |
| WHERE vs HAVING | Rows before grouping · groups after |
| DELETE vs TRUNCATE vs DROP | Some rows · all rows · the whole table |
| Logical vs physical design | Tables, columns, keys · indexes, structures, partitions |
| Candidate vs primary vs artificial key | Unique + minimal · the one chosen · designer-made integer |
| 3NF vs BCNF | Rule covers non-key columns · rule covers every column |
| Normalization vs denormalization | Split to remove redundancy · merge to add it back |
| Dense vs sparse index | Entry per row · entry per block |
| Table scan vs index scan | Best for high hit ratio · best for low hit ratio |
| View vs materialized view | Runs its query on use · stores data, needs refreshing |
| Strong vs weak entity | Own identifying attribute · depends on an identifying relationship |
| `%` vs `_` in LIKE | Any number of characters · exactly one |
| Heap vs sorted vs hash table | Fast inserts · fast ranges · fast exact matches |
| Unary vs binary vs ternary | One entity type · two · three |
| Cardinality vs modality | Maximum (one or many) · minimum (zero or one) |
| Select vs project (algebra) | Picks rows · picks columns |

## Before you walk in

- [ ] Write the clause order from memory
- [ ] Name the 5 sublanguages and one statement each
- [ ] Say which rows survive each of the 5 joins
- [ ] List the 8 design steps (4 analysis, 4 logical)
- [ ] State 1NF, 2NF, 3NF, BCNF in one line each
- [ ] Name the 4 referential integrity actions
- [ ] Read crow's foot: circle, line, crow's foot
- [ ] Name a relationship by asking "one or many?" from both sides

[← All modules](README.md)
