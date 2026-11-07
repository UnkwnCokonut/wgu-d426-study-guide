# 8. Design and ER modeling

**Time:** 6 minutes

> [!TIP]
> **TL;DR**
> - Three phases: **Analysis → Logical design → Physical design**.
> - Eight steps: four in analysis, four in logical design. The last analysis step is **supertype/subtype**.
> - Crow's foot: **circle = 0, line = 1, crow's foot = many**.
> - Name a relationship by asking "one or many?" **from both sides**.

## Phases and steps

```mermaid
flowchart TD
  subgraph A["Analysis: ER model, no specific DB"]
    a1["1 Discover entities,<br/>relationships, attributes"] --> a2["2 Determine cardinality"] --> a3["3 Strong vs weak entities"] --> a4["4 Supertype / subtype"]
  end
  subgraph L["Logical design: tables + keys"]
    l5["5 Implement entities"] --> l6["6 Implement relationships"] --> l7["7 Implement attributes"] --> l8["8 Apply normal form"]
  end
  a4 --> l5
  l8 --> P["Physical design<br/>indexes, storage"]
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

## Naming the relationship (exam favorite)

The question's wording can trick you. **Ask it from both sides**, out loud:

1. "Can one A have many B?"
2. "Can one B have many A?"

| Both answers | Relationship | Example |
| --- | --- | --- |
| Yes and yes | **Many-to-many (M:M)** | Employees ↔ projects, students ↔ classes, doctors ↔ patients |
| Yes and no | **One-to-many / many-to-one** | Many employees → one office building |
| No and no | **One-to-one (1:1)** | Employee ↔ desk, when desks are never shared |

"Employee works on project" *sounds* one-to-one. It isn't: projects have many employees, and employees can be on many projects.

**Degree** = how many entity types are involved:

- **Unary:** one entity type related to itself (Employee supervises Employee).
- **Binary:** two entity types. The usual case.
- **Ternary:** three entity types.

**Modality** is another name for the relationship **minimum** (optional vs required). Cardinality usually means the maximum.

## Strong, weak, super, sub

- **Strong entity:** has its own identifying attribute.
- **Weak entity:** doesn't; depends on an **identifying relationship** to an **identifying entity** (an order line item depends on its order).
- On the diagram, a **diamond** sits next to the identifying entity. Its cardinality there is always **1(1)**.
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

<details><summary>4. Students take many classes; classes have many students. Relationship?</summary>

**Many-to-many.**
</details>

[← Back](07-joins-subqueries-views.md) · [Next: Normalization →](09-normalization.md)
