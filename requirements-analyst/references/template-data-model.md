# Data Model Template

**Output File**: `specs/[feature-name]/data-model.md`

**Standards**: Follow `diagram-standards.md`

```markdown
# Data Model: [Feature Name]

**Created**: [Date]
**Last Updated**: [Date]
**Status**: Draft | Review | Approved

---

## 1. Data Model Overview

### 1.1 Entity Relationship Diagram

\`\`\`mermaid
erDiagram
    ENTITY_A ||--o{ ENTITY_B : "has"
    ENTITY_A {
        string id PK
        string name
        datetime created_at
    }
    ENTITY_B {
        string id PK
        string entity_a_id FK
        string status
    }
\`\`\`

### 1.2 Entity Summary

| Entity | Description | Key Attributes | Relationships |
|--------|-------------|----------------|---------------|
| **Entity A** | [Description] | id, name | Has many Entity B |

---

## 2. Entity Definitions

### 2.1 [Entity Name]

| Property | Value |
|----------|-------|
| **Entity ID** | ENT-001 |
| **Description** | [What it represents] |
| **Aggregate Root** | Yes / No |

#### Attributes

| Attribute | Type | Required | Unique | Default | Description | Constraints |
|-----------|------|----------|--------|---------|-------------|-------------|
| `id` | string | Yes | Yes | UUID | Primary identifier | UUID v4 |
| `name` | string | Yes | No | - | Display name | 1-100 chars |
| `status` | enum | Yes | No | `active` | Current status | [active, inactive] |
| `created_at` | datetime | Yes | No | NOW() | Creation timestamp | ISO 8601 |

#### Business Rules

| Rule ID | Rule | Validation |
|---------|------|------------|
| BR-001 | [Rule] | [How to validate] |

#### Indexes

| Index Name | Columns | Type | Purpose |
|------------|---------|------|---------|
| `idx_name` | name | B-tree | Search optimization |

---

## 3. Relationships

| From | Relationship | To | Cardinality | Cascade Delete |
|------|-------------|-----|-------------|----------------|
| Entity A | has | Entity B | 1:N | Yes / No |

---

## 4. State Diagrams

### 4.1 [Entity Name] Lifecycle

\`\`\`mermaid
stateDiagram-v2
    [*] --> Draft: Create
    Draft --> Pending: Submit
    Draft --> Cancelled: Cancel
    Pending --> Approved: Approve
    Pending --> Rejected: Reject
    Approved --> Active: Activate
    Active --> Completed: Complete
    Completed --> [*]
    Cancelled --> [*]
\`\`\`

### State Definitions

| State | Description | Allowed Transitions |
|-------|-------------|---------------------|
| Draft | Initial state | Submit, Cancel |
| Pending | Awaiting approval | Approve, Reject |

---

## 5. Data Constraints

### Validation Rules

| Constraint ID | Entity | Field | Rule | Error Message |
|---------------|--------|-------|------|---------------|
| VAL-001 | User | email | Valid email format | "Invalid email" |

### Referential Integrity

| Parent | Child | On Delete | On Update |
|--------|-------|-----------|-----------|
| Entity A | Entity B | CASCADE | CASCADE |

---

## 6. Data Volume Estimates

| Entity | Initial | Monthly Growth | 1-Year Projection | Storage/Record |
|--------|---------|----------------|-------------------|----------------|
| User | 1,000 | +500/month | 7,000 | ~2 KB |

---

## 7. Data Dictionary

### Standard Types

| Type | Format | Example |
|------|--------|---------|
| `id` | UUID v4 | `550e8400-...` |
| `email` | RFC 5322 | `user@example.com` |
| `currency` | 2 decimals | `99.99` |
| `datetime` | ISO 8601 | `2024-01-15T10:30:00Z` |

### Enumerations

| Value | Label | Description |
|-------|-------|-------------|
| `active` | Active | Currently active |

---

## 8. Domain Glossary

| Term | Definition | Related Entities |
|------|------------|------------------|
| **[Term]** | [Definition] | Entity A |

---

## 9. Traceability

| Entity | Source Requirements | User Stories |
|--------|---------------------|--------------|
| Entity A | REQ-001 | US-001 |
```
