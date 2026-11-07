# 8. Design and ER modeling

**Time:** 6 minutes

> [!TIP]
> **TL;DR**
> - Three phases: **Analysis → Logical design → Physical design**.
> - Eight steps: four in analysis, four in logical design. The last analysis step is **supertype/subtype**.
> - Crow's foot: **circle = 0, line = 1, crow's foot = many**.

## Phases and steps

```mermaid
flowchart LR
  subgraph A["Analysis (ER model, no specific DB)"]
    a1["1 Discover entities,<br/>relationships, attributes"] --> a2["2 Cardinality"] --> a3["3 Strong / weak"] --> a4["4 Supertype / subtype"]
  end
  subgraph L["Logical design (tables, keys)"]
    l5["5 Implement entities"] --> l6["6 Implement relationships"] --> l7["7 Implement attributes"] --> l8["8 Apply normal form"]
  end
  a4 --> l5
  L --> P["Physical design<br/>indexes, storage"]
```

- **Analysis** is also called conceptual design, ER modeling, or requirements definition.
- **Physical design** never changes results, only speed.

## ER building blocks

| Thing | What it is | Becomes |
| --- | --- | --- |
| **Entity** | Person, place, product, concept, activity (rectangle) | Table |
| **Relationship** | A statement about two entities | Foreign key |
| **Attribute** | A descriptive property | Column |

- **Reflexive relationship:** an entity related to itself.
- **Type vs instance:** "all employees" is a type; "Sam Snead" is an instance.
- **Intangible entity:** in the model, but not tracked with data.

## Cardinality

- **Relationship maximum:** the most instances that can relate (one or many).
- **Relationship minimum:** the fewest (zero = optional, one = required).
- **Attribute notation:** `Name 1(1)` = singular, required. `Phone M(0)` = plural, optional.

| Crow's foot | Means |
| --- | --- |
| Circle | Zero |
| Short line | One |
| Three lines | Many |

## Strong, weak, super, sub

- **Strong entity:** has its own identifying attribute.
- **Weak entity:** doesn't; depends on an **identifying relationship** (an order line item depends on its order).
- **Subtype:** a subset of a **supertype** (Manager in Employee). Drawn inside it, linked by an **IsA** relationship.
- **Partition:** a group of **mutually exclusive** subtypes (Car, Truck, Motorcycle in Vehicle).

> [!WARNING]
> **Exam traps**
> - "Apply normal form" is step 8, in **logical design**, not analysis.
> - Weak ≠ intangible. Weak lacks an identifier; intangible isn't stored at all.

## Quick check

<details><summary>1. Last of the four analysis steps?</summary>

**Create supertype and subtype entities.**
</details>

<details><summary>2. Circle + crow's foot means…?</summary>

**Zero or many.**
</details>

<details><summary>3. Relationship type becomes what in logical design?</summary>

**A foreign key.**
</details>

[← Back](07-joins-subqueries-views.md) · [Next: Normalization →](09-normalization.md)
