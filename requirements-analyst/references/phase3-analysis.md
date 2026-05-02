# Phase 3: Requirements Analysis

**Objective**: Deep analysis of dependencies, feasibility, and implementation approaches.
**Time Allocation**: 20% of total effort
**Role**: Professional Requirements Analyst

## Quick Reference

| Method | Focus | Output |
|--------|-------|--------|
| User Story Mapping | User activities and priorities | Story map with MVP |
| Use Case Analysis | Actor-system interactions | Use case documents |
| Success Criteria | Measurable outcomes | SMART criteria list |
| Event Storming | Domain events and commands | Domain model |
| Dependency Analysis | Requirement relationships | Dependency graph |
| Domain Data Modeling | Entities and relationships | data-model.md |
| NFR Analysis | System qualities | NFR specification |

## Output

**Files**:
- `specs/[feature-name]/requirements.md` — User stories, use cases, success criteria, dependencies
- `specs/[feature-name]/data-model.md` — Entity definitions, relationships, state diagrams

**Templates**: Read `references/template-analysis.md` and `references/template-data-model.md`
**Standards**: Follow `references/diagram-standards.md` for all diagrams.

## Pre-Check

- Phase 2 completed? `sort.md` exists with value sorting?
- Inputs available? Prioritization (MoSCoW/RICE) complete?
- If `clarification.md` or `validation.md` already exist, load and reference them (this is an iteration).

If any check fails: STOP and return to Phase 2.

## Iterative Analysis

If `clarification.md` exists: read it, extract resolved Q&A, apply to analysis, mark updates with `[Updated per Clarification Q1]`.

If `validation.md` exists: read it, extract issues by dimension, address each in the relevant section, mark with `[Updated per Validation V-001]`.

---

## Method 1: User Story Mapping

### Core User Activity Flow (UML Activity Diagram)

Use `stateDiagram-v2` for user activity flows:

```mermaid
stateDiagram-v2
    [*] --> Browse: Start

    Browse --> Select
    Select --> Decision1

    state Decision1 <<choice>>
    Decision1 --> Purchase: [Add to Cart]
    Decision1 --> Browse: [Continue Shopping]

    Purchase --> Payment
    Payment --> Decision2

    state Decision2 <<choice>>
    Decision2 --> Receive: [Success]
    Decision2 --> Purchase: [Retry]

    Receive --> Support
    Support --> [*]: End
```

**Activity Diagram Elements:**
| Element | UML Standard | Mermaid Syntax |
|---------|--------------|----------------|
| Start Node | Filled circle | `[*] -->` |
| End Node | Bull's eye | `--> [*]` |
| Activity | Rounded rectangle | `StateName: Label` |
| Decision | Diamond | `state Name <<choice>>` |
| Transition | Arrow with guard | `--> Target: [condition]` |
| Fork/Join | Thick bar | `state Name { ... }` |

### User Story Format

```
As a [role],
I want [feature/capability],
So that [business value/benefit].
```

Each story must pass INVEST: Independent, Negotiable, Valuable, Estimable, Small, Testable.

### Story Map Visualization

Use `graph TB` with subgraphs to create a matrix: Activities across the top (user flow), releases down (MVP → v1.1 → v2.0).

```mermaid
graph TB
    subgraph Activities["USER ACTIVITY FLOW →"]
        direction LR
        A1["Activity 1<br/>Browse"]
        A2["Activity 2<br/>Select"]
        A3["Activity 3<br/>Purchase"]
        A4["Activity 4<br/>Receive"]
        A1 --> A2 --> A3 --> A4
    end

    subgraph MVP["MVP Release"]
        direction LR
        S11[US-1.1] --> S21[US-2.1] --> S31[US-3.1] --> S41[US-4.1]
        S12[US-1.2] --> S22[US-2.2] --> S32[US-3.2]
    end

    subgraph V11["Version 1.1"]
        direction LR
        S13[US-1.3] --> S23[US-2.3] --> S33[US-3.3] --> S42[US-4.2]
    end

    A1 -.-> S11
    A1 -.-> S13

    style A1 fill:#e1f5fe,stroke:#01579b
    style A2 fill:#e1f5fe,stroke:#01579b
    style A3 fill:#e1f5fe,stroke:#01579b
    style A4 fill:#e1f5fe,stroke:#01579b
```

**Story Map Structure:**
| Row | Description | Priority |
|-----|-------------|----------|
| **Activities** | User journey steps (left to right) | - |
| **MVP** | Minimum stories to launch | P0 |
| **V1.1** | First enhancement release | P1 |
| **V2.0** | Future features | P2 |

---

## Method 2: Use Case Analysis

### Use Case Diagram

Draw use case diagrams with actors (stick figures), use cases (ellipses), system boundary (subgraph), and `<<include>>`/`<<extend>>` relationships.

```mermaid
graph TB
    subgraph System["System Boundary"]
        direction TB
        UCA((Use Case A))
        UCB((Use Case B))
        UCC((Use Case C))
        UCD((Use Case D))

        UCA -->|<<include>>| UCC
        UCA --> UCB
        UCB -.->|<<extend>>| UCD
    end

    Actor1[/"Actor 1"\]
    Actor2[/"Actor 2"\]

    Actor1 --> UCA
    Actor2 --> UCB

    style UCA fill:#e1f5fe,stroke:#01579b
    style UCB fill:#e1f5fe,stroke:#01579b
    style UCC fill:#e1f5fe,stroke:#01579b
    style UCD fill:#fff3e0,stroke:#e65100
```

**Diagram Elements:**
| Element | Mermaid Syntax | Description |
|---------|----------------|-------------|
| Actor | `[/"Name"\]` | Stick figure representation |
| Use Case | `((Name))` | Ellipse shape |
| System Boundary | `subgraph` | Dashed rectangle container |
| Include | `-->|<<include>>|` | Mandatory dependency |
| Extend | `-.->|<<extend>>|` | Optional extension |

### Use Case Document

For each use case, document: Basic Info, Preconditions, Postconditions, Main Flow (as Sequence Diagram), Alternative Flows, Exception Flows, Business Rules, and NFRs.

The main flow of every use case requires a Sequence Diagram — actor-system tables alone are insufficient.

```mermaid
sequenceDiagram
    autonumber
    actor User as User
    participant UI as Interface
    participant System as System
    participant DB as Database

    User->>UI: 1. Initiate Request
    activate UI
    UI->>System: 2. Forward Request
    activate System
    alt Success
        System-->>UI: 3. Success Response
    else Failure
        System-->>UI: 3. Error Response
    end
    deactivate System
    deactivate UI
```

---

## Method 3: Success Criteria

Define SMART criteria for each requirement:

| Attribute | Description |
|-----------|-------------|
| Specific | Clear and unambiguous |
| Measurable | Quantifiable metric |
| Achievable | Realistic given constraints |
| Relevant | Aligned with business goals |
| Time-bound | Has defined timeframe |

Categories: Functional, Performance, Usability, Business, Quality.

### Success Criteria Traceability

```mermaid
graph LR
    subgraph Requirements
        REQ[REQ-001<br/>Requirement]
        US[US-001<br/>User Story]
    end

    subgraph SuccessCriteria[Success Criteria]
        SC1[SC-001<br/>Functional]
        SC2[SC-002<br/>Performance]
        SC3[SC-003<br/>Business]
    end

    subgraph Verification
        TC[Test Cases]
        KPI[KPIs]
        MON[Monitoring]
    end

    REQ --> SC1
    REQ --> SC2
    US --> SC3
    SC1 --> TC
    SC2 --> MON
    SC3 --> KPI

    style REQ fill:#e1f5fe,stroke:#01579b
    style US fill:#e1f5fe,stroke:#01579b
    style SC1 fill:#e8f5e9,stroke:#1b5e20
    style SC2 fill:#e8f5e9,stroke:#1b5e20
    style SC3 fill:#e8f5e9,stroke:#1b5e20
```

### Example Success Criteria

| SC ID | Requirement | Category | Metric | Target |
|-------|-------------|----------|--------|--------|
| SC-001 | US-001 Login | Functional | Login success rate | >= 99.5% |
| SC-002 | US-001 Login | Performance | Login response time | < 1 second |
| SC-003 | US-001 Login | Security | Failed login lockout | After 5 attempts |
| SC-004 | US-002 Search | Usability | Search result relevance | >= 90% accuracy |
| SC-005 | REQ-010 | Business | User retention | >= 80% after 30 days |

---

## Method 4: Event Storming (Complex Systems)

Identify Domain Events (orange), Commands (blue), Aggregates (yellow), Policies (purple), Read Models (green), External Systems (pink), Hot Spots (red/unresolved).

### Event Storming Output

```
[User] → [Command] → [Aggregate] → [Domain Event] → [Policy] → [Next Command]
```

| Element | Description | Example |
|---------|-------------|---------|
| Domain Event | Something that happened | "Order Placed" |
| Command | Action that triggers event | "Place Order" |
| Aggregate | Entity that receives command | "Order" |
| Policy | Reaction rule | "When order placed, notify warehouse" |
| Read Model | Data needed for decision | "Available inventory" |
| External System | Third-party integration | "Payment Gateway" |
| Hot Spot | Unresolved question | "How to handle split shipment?" |

---

## Method 5: Dependency Analysis

### Dependency Types

| Type | Description | Risk Level |
|------|-------------|------------|
| Mandatory | Must complete A before B | High |
| Optional | A enhances B | Low |
| Conflicting | A and B cannot coexist | Critical |
| External | Depends on outside system | High |

### Dependency Graph

```mermaid
graph LR
    REQ001[REQ-001]
    REQ002[REQ-002]
    REQ005[REQ-005]
    REQ008[REQ-008]
    REQ012[REQ-012]

    REQ001 --> REQ005
    REQ002 --> REQ005
    REQ005 --> REQ008
    REQ003 -.->|optional| REQ012

    style REQ001 fill:#e1f5fe,stroke:#01579b
    style REQ002 fill:#e1f5fe,stroke:#01579b
    style REQ012 fill:#fff3e0,stroke:#e65100
```

### Critical Path

```mermaid
graph LR
    CP1[REQ-001<br/>User Registration] --> CP2[REQ-005<br/>Profile Setup]
    CP2 --> CP3[REQ-008<br/>Data Validation]
    CP3 --> CP4[REQ-011<br/>Account Activation]

    style CP1 fill:#ffebee,stroke:#b71c1c
    style CP2 fill:#ffebee,stroke:#b71c1c
    style CP3 fill:#ffebee,stroke:#b71c1c
    style CP4 fill:#ffebee,stroke:#b71c1c
```

Map requirement dependencies: Mandatory, Optional, Conflicting, External. Identify the critical path and bottlenecks.

---

## Method 6: Domain Data Modeling

Create `data-model.md` with: ER Diagram (Mermaid), Entity Definitions (attributes, types, constraints), Relationships, State Diagrams for entity lifecycles, Validation Rules, Data Volume Estimates, and Glossary.

### ER Diagram Example

```mermaid
erDiagram
    USER ||--o{ ORDER : "places"
    USER {
        string id PK
        string email UK
        string name
        enum status
        datetime created_at
    }
    ORDER ||--|{ ORDER_ITEM : "contains"
    ORDER {
        string id PK
        string user_id FK
        decimal total
        enum status
        datetime created_at
    }
    ORDER_ITEM {
        string id PK
        string order_id FK
        string product_id FK
        int quantity
        decimal price
    }
    PRODUCT ||--o{ ORDER_ITEM : "included_in"
    PRODUCT {
        string id PK
        string name
        decimal price
        int stock
    }
```

### State Diagram Example

```mermaid
stateDiagram-v2
    [*] --> Draft: Create
    Draft --> Submitted: Submit
    Draft --> Cancelled: Cancel
    Submitted --> Approved: Approve
    Submitted --> Rejected: Reject
    Approved --> Active: Activate
    Rejected --> Draft: Revise
    Active --> Completed: Complete
    Active --> Cancelled: Cancel
    Completed --> [*]
    Cancelled --> [*]
```

---

## Method 7: NFR Analysis (FURPS+ Model)

| Category | Key Questions |
|----------|---------------|
| Performance | Response time? Throughput? Concurrent users? |
| Security | Auth? Encryption? Audit? |
| Reliability | Uptime SLA? Failover? Recovery? |
| Usability | WCAG? Learnability? Error handling? |
| Scalability | Horizontal/vertical? Data volume growth? |
| Maintainability | Logging? Monitoring? Deployment? |
| Compatibility | Browsers? Devices? Third-party? |

Each NFR must have: Category, Priority, Related FR, Measurable Target, and Verification Method.

### NFR by Category Examples

#### Performance

| NFR ID | Requirement | Metric | Target |
|--------|-------------|--------|--------|
| NFR-P01 | Page load time | Time to First Contentful Paint | < 1.5s |
| NFR-P02 | API response time | 95th percentile latency | < 200ms |
| NFR-P03 | Concurrent users | Simultaneous active sessions | >= 10,000 |
| NFR-P04 | Throughput | Transactions per second | >= 1,000 TPS |

#### Security

| NFR ID | Requirement | Metric | Target |
|--------|-------------|--------|--------|
| NFR-S01 | Authentication | Multi-factor authentication | Required for admin |
| NFR-S02 | Data encryption | Encryption at rest | AES-256 |
| NFR-S03 | Data encryption | Encryption in transit | TLS 1.3 |
| NFR-S04 | Session management | Session timeout | 30 min inactive |
| NFR-S05 | Audit logging | Security events logged | 100% coverage |

#### Reliability

| NFR ID | Requirement | Metric | Target |
|--------|-------------|--------|--------|
| NFR-R01 | Availability | Uptime SLA | 99.9% (8.76h downtime/year) |
| NFR-R02 | Disaster recovery | Recovery Time Objective (RTO) | < 4 hours |
| NFR-R03 | Data durability | Recovery Point Objective (RPO) | < 1 hour |
| NFR-R04 | Backup | Backup frequency | Daily full, hourly incremental |

#### Usability

| NFR ID | Requirement | Metric | Target |
|--------|-------------|--------|--------|
| NFR-U01 | Accessibility | WCAG compliance | Level AA |
| NFR-U02 | Learnability | Time to complete key task (new user) | < 5 min |
| NFR-U03 | Error recovery | User can recover from error | Without data loss |
| NFR-U04 | Localization | Supported languages | EN, ZH-CN |

#### Scalability

| NFR ID | Requirement | Metric | Target |
|--------|-------------|--------|--------|
| NFR-SC01 | Horizontal scaling | Auto-scale trigger | CPU > 70% |
| NFR-SC02 | Data growth | Storage capacity plan | 100GB/year growth |
| NFR-SC03 | User growth | Support user base | 1M users by Year 2 |

#### Maintainability

| NFR ID | Requirement | Metric | Target |
|--------|-------------|--------|--------|
| NFR-M01 | Logging | Log retention | 90 days |
| NFR-M02 | Monitoring | System health dashboard | Real-time |
| NFR-M03 | Deployment | Deployment frequency | On-demand, < 30min |
| NFR-M04 | Documentation | API documentation | 100% coverage |

#### Compatibility

| NFR ID | Requirement | Metric | Target |
|--------|-------------|--------|--------|
| NFR-C01 | Browser support | Supported browsers | Chrome, Firefox, Safari, Edge (latest 2) |
| NFR-C02 | Mobile support | Responsive design | iOS 14+, Android 10+ |
| NFR-C03 | API compatibility | API versioning | Backward compatible for 2 major versions |

### NFR Prioritization Matrix

```mermaid
quadrantChart
    title NFR Priority Matrix
    x-axis Low Impact --> High Impact
    y-axis Low Effort --> High Effort
    quadrant-1 Plan Carefully
    quadrant-2 High Priority
    quadrant-3 Low Priority
    quadrant-4 Quick Wins
    Performance: [0.8, 0.6]
    Security: [0.9, 0.7]
    Reliability: [0.85, 0.8]
    Usability: [0.6, 0.4]
    Scalability: [0.7, 0.75]
```

---

## Exit Criteria

| Criteria | Standard |
|----------|----------|
| Diagram Standards | All diagrams follow UML/Mermaid standards |
| User Story Map | Core user journeys mapped |
| Use Case Diagrams | Main use cases with Sequence Diagrams |
| Success Criteria | SMART criteria for key requirements |
| Data Model | `data-model.md` with ER and state diagrams |
| NFR Analysis | All categories reviewed with measurable targets |
| Dependency Graph | Dependencies mapped, no circular |
| Feasibility | Technical risks evaluated |

## Next Step

Phase 4: Clarification — Systematic questioning to eliminate ambiguity.
