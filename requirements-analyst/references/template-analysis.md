# Analysis Output Template

**Output Files**:
- `specs/[feature-name]/requirements.md` — This template
- `specs/[feature-name]/data-model.md` — See `template-data-model.md`

**Standards**: Follow `diagram-standards.md`

```markdown
# Analysis: [Feature Name]

**Created**: [Date]
**Status**: In Progress | Completed

---

## 1. User Personas

| Persona | Description | Key Goals |
|---------|-------------|-----------|
| [Persona 1] | [Brief description] | [Primary goals] |

---

## 2. Core User Activity Flow

### Activity Diagram

\`\`\`mermaid
stateDiagram-v2
    [*] --> Activity1: Start
    Activity1 --> Decision1
    state Decision1 <<choice>>
    Decision1 --> Activity2: [Condition A]
    Decision1 --> Activity3: [Condition B]
    Activity2 --> Activity4
    Activity3 --> Activity4
    Activity4 --> [*]: End
\`\`\`

### Activity Details

| Activity | Description | Input | Output | Participants |
|----------|-------------|-------|--------|--------------|
| **Activity 1** | [Description] | [Input] | [Output] | [Who] |

---

## 3. User Story Map

| Activity | MVP | v1.1 | v2.0 |
|----------|-----|------|------|
| **[Activity 1]** | US-001, US-002 | US-003 | US-004 |

---

## 4. User Stories

### Activity 1: [Activity Name]

#### US-001: [Story Title]

**Priority**: P0 | P1 | P2
**Persona**: [Which persona]
**Release**: MVP | v1.1 | v2.0

**Story**:
> As a [role],
> I want [feature/capability],
> So that [business value/benefit].

**Acceptance Criteria**:

\`\`\`gherkin
Scenario: [Scenario name]
  Given [precondition]
  When [action]
  Then [expected result]
\`\`\`

**INVEST Check**:
- [ ] Independent
- [ ] Negotiable
- [ ] Valuable
- [ ] Estimable
- [ ] Small
- [ ] Testable

---

## 5. Use Case Diagram

\`\`\`mermaid
graph TB
    subgraph SystemBoundary["System Boundary"]
        direction TB
        UC1((UC-001))
        UC2((UC-002))
        UC1 -->|<<include>>| UC2
    end
    Actor1[/"👤 Actor 1"\]
    Actor1 --> UC1
    style UC1 fill:#e1f5fe,stroke:#01579b
\`\`\`

### Use Case List

| UC ID | Name | Primary Actor | Priority | Description |
|-------|------|---------------|----------|-------------|
| **UC-001** | [Name] | [Actor] | P0 | [Brief] |

---

## 6. Use Case Details

### UC-001: [Use Case Name]

| Field | Value |
|-------|-------|
| **Use Case ID** | UC-001 |
| **Name** | [Descriptive name] |
| **Primary Actor** | [Who initiates] |
| **Priority** | P0 / P1 / P2 |

#### Main Flow Sequence Diagram

\`\`\`mermaid
sequenceDiagram
    autonumber
    actor User as 👤 User
    participant UI as 🖥️ Interface
    participant System as ⚙️ System
    participant DB as 🗄️ Database

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
\`\`\`

#### Preconditions
1. [Condition]

#### Postconditions (Success)
1. [State after completion]

#### Alternative Flows

**A1: [Name]**
- **Trigger**: [When]
- **Description**: [What happens]

#### Exception Flows

**E1: [Name]**
- **Trigger**: [What causes this]
- **System Response**: "[Error message]"
- **Recovery**: [How to recover]

---

## 7. Success Criteria

| SC ID | Requirement | Category | Metric | Target | Verification |
|-------|-------------|----------|--------|--------|--------------|
| **SC-001** | US-001 | Functional | [Metric] | [Target] | [Method] |

---

## 8. Dependency Analysis

### Dependency Graph

\`\`\`mermaid
graph TD
    REQ001[REQ-001] --> REQ002[REQ-002]
    REQ001 --> REQ003[REQ-003]
    REQ002 --> REQ004[REQ-004]
    EXT[External API] -.-> REQ003
    style REQ001 fill:#e1f5fe
    style EXT fill:#fff3e0
\`\`\`

### Dependency Matrix

| Req ID | Depends On | Type | Impact if Delayed |
|--------|------------|------|-------------------|
| **REQ-002** | REQ-001 | Mandatory | Blocks feature |

---

## 9. Feasibility Assessment

| Requirement | Technical Feasibility | Risk Level | Notes |
|-------------|----------------------|------------|-------|
| **REQ-001** | High | Low | Standard implementation |

---

## 10. Non-Functional Requirements (NFR)

### NFR Summary

| Category | Count | Priority Distribution |
|----------|-------|----------------------|
| Performance | [N] | P0: [n], P1: [n] |
| Security | [N] | P0: [n], P1: [n] |

### [Category] Requirements

| NFR ID | Requirement | Metric | Target | Related FR |
|--------|-------------|--------|--------|------------|
| NFR-P01 | [Requirement] | [Metric] | [Target] | US-XXX |

---

## 11. Analysis Update Log (If Iterating)

### Applied from clarification.md

| Q# | Clarification Summary | Applied To | Section Updated |
|----|----------------------|------------|-----------------|

### Applied from validation.md

| Issue ID | Validation Finding | Applied To | Section Updated |
|----------|-------------------|------------|-----------------|

---

## 12. Analysis Summary

**User Roles Identified**: [List]
**Core Activities**: [List]
**Key Findings**: [List]
**Risks Identified**: [List with mitigation]

---

## 13. Related Artifacts

> See `data-model.md` for complete data structure definitions

---

## 14. Next Steps

- [ ] Proceed to Phase 4: Clarify (Requirements Clarification)
```
