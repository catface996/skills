# PRD (Product Requirements Document) Template

**Output File**: `specs/[feature-name]/prd.md`

**Source Documents**: discovery.md, sort.md, requirements.md, clarification.md, validation.md

```markdown
# Product Requirements Document (PRD)

# [Product/Feature Name]

---

## Document Information

| Field | Value |
|-------|-------|
| **Product Name** | [Name] |
| **Version** | v1.0.0 |
| **Creation Date** | [Date] |
| **Last Updated** | [Date] |
| **Owner** | [Name] |
| **Status** | Draft / In Review / Approved |

### Document History

| Version | Date | Author | Changes | Approved By |
|---------|------|--------|---------|-------------|
| 0.1 | [Date] | [Name] | Initial draft | - |

### Related Documents

| Document | Location | Description |
|----------|----------|-------------|
| Discovery | `specs/[name]/discovery.md` | Stakeholder analysis |
| Analysis | `specs/[name]/requirements.md` | Detailed requirements |
| Clarification | `specs/[name]/clarification.md` | Decision log |
| Validation | `specs/[name]/validation.md` | Validation report |
| API Spec | `specs/[name]/api.yaml` | API contract |
| RTM | `specs/[name]/rtm.md` | Traceability matrix |

---

## 1. Executive Summary

### 1.1 Overview
[2-3 paragraphs: What, what problem, who, key benefits]

### 1.2 Key Highlights

| Aspect | Summary |
|--------|---------|
| **Target Users** | [Personas] |
| **Core Value** | [Value proposition] |
| **MVP Scope** | [Key features] |
| **Timeline** | [Target date] |
| **Success Metric** | [Primary KPI] |

### 1.3 Validation Status

| Dimension | Score | Status |
|-----------|-------|--------|
| Authenticity | [X]% | ✅/⚠️/❌ |

---

## 2. Product Overview

### 2.1 Product Vision
[Long-term vision, 2-3 years]

### 2.2 Problem Statement

| Aspect | Description |
|--------|-------------|
| **Current State** | [How things work today] |
| **Pain Points** | [Problems users face] |
| **Impact** | [Business/user impact] |
| **Evidence** | [Supporting data] |

### 2.3 Product Objectives

| ID | Objective | Success Metric | Target |
|----|-----------|----------------|--------|
| OBJ-001 | [Objective] | [Metric] | [Value] |

### 2.4 Scope

#### In Scope
| ID | Feature | Release | Priority |
|----|---------|---------|----------|
| S-001 | [Feature] | MVP | P0 |

#### Out of Scope
| Item | Reason | Future |
|------|--------|--------|
| [Item] | [Why] | v2.0 / Never |

#### Assumptions & Constraints
[Tables for assumptions and constraints]

---

## 3. User Analysis

### 3.1 Personas
[Persona cards with role, demographics, goals, pain points, behaviors]

### 3.2 User Journey Map
[Mermaid journey diagram]

### 3.3 Core Activity Flow
[stateDiagram-v2 activity diagram]

---

## 4. Functional Requirements

### 4.1 Requirements Summary
[Priority table]

### 4.2 User Story Map
[Activity × Release matrix]

### 4.3 Feature: [Name]
[Overview, User Stories with GWT acceptance criteria, Business Rules, Data Requirements]

---

## 5. Use Cases

### 5.1 Use Case Diagram
[Mermaid graph with actors, use cases, system boundary]

### 5.2 Use Case Details
[For each: info, preconditions, postconditions, main flow sequence diagram, alternative/exception flows]

---

## 6. Domain Model

### 6.1 ER Diagram
[Mermaid erDiagram]

### 6.2 Entity Definitions
[Attribute tables with types and constraints]

### 6.3 State Diagrams
[stateDiagram-v2 for entities with lifecycle]

---

## 7. Non-Functional Requirements
[Performance, Scalability, Availability, Security, Usability, Compliance — each with quantified targets]

---

## 8. Interface Specifications
[UI screen inventory, wireframe links, navigation structure, API endpoints, external integrations]

---

## 9. Error Handling
[Error categories, message specifications, recovery procedures]

---

## 10. Clarification Decisions
[From Phase 4: question log and key decisions]

---

## 11. Dependencies & Risks
[Dependency graph, critical path, external dependencies, risk register]

---

## 12. Release Plan
[MVP scope, version roadmap with Gantt chart]

---

## 13. Success Criteria & KPIs
[Metrics, acceptance criteria summary, definition of done]

---

## 14. Glossary
[Term definitions]

---

## 15. Appendices
[References, open questions, change log]

---

## Approvals

| Role | Name | Decision | Date | Comments |
|------|------|----------|------|----------|
| Product Owner | [Name] | Approved/Rejected | [Date] | [Comments] |
| Technical Lead | [Name] | Approved/Conditional | [Date] | [Conditions] |
```
