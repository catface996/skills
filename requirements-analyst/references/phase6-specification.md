# Phase 6: Requirements Specification

**Objective**: Formalize validated requirements into unified documentation, establish requirements baseline.
**Time Allocation**: 10% of total effort
**Role**: Professional Requirements Analyst

## Deliverables

| Deliverable | Format | Mandatory? |
|-------------|--------|------------|
| PRD Document | Markdown | Yes |
| API Specification | OpenAPI YAML | If API-heavy |
| RTM | Markdown | Yes |
| Requirements Baseline | Version controlled | Yes |

## Output

**Primary**: `specs/[feature-name]/prd.md`
**Additional**: `api.yaml` (OpenAPI), `rtm.md` (Traceability Matrix)

**Templates**: Read `references/template-prd.md`, `references/template-openapi.md`, `references/template-rtm.md`

## Pre-Check

- Phase 5 complete? ALL validation criteria satisfied?
- All requirements validated and approved?
- Stakeholder alignment achieved?

If any check fails: STOP and return to Phase 5.

## Custom Template Support

Before generating specification documents, ask the user about custom templates:

| Option | Description |
|--------|-------------|
| A | Use default templates |
| B | Use custom template (user provides path) |
| C | Start with custom, supplement with defaults |

If custom: validate template, identify placeholders, report structure, confirm before proceeding.

Template search locations: User-provided path → project `templates/` directory → Built-in templates.

## Method 1: PRD Document

Consolidates all prior phases into one authoritative document:

1. Document Information (version, owner, status)
2. Executive Summary (overview, key highlights, validation status)
3. Product Overview (vision, problem, objectives, scope, assumptions, constraints)
4. User Analysis (personas, journey maps, activity flows)
5. Functional Requirements (summary, story map, features with user stories + GWT acceptance criteria)
6. Use Cases (diagrams, details with sequence diagrams)
7. Domain Model (ER diagram, entity definitions, state diagrams)
8. Non-Functional Requirements (performance, scalability, availability, security, usability, compliance)
9. Interface Specifications (UI screens, API endpoints, external integrations)
10. Error Handling (categories, messages, recovery procedures)
11. Clarification Decisions (from Phase 4)
12. Dependencies & Risks (dependency graph, critical path, risk register)
13. Release Plan (MVP scope, roadmap)
14. Success Criteria & KPIs
15. Glossary, Appendices, Approvals

## Method 2: API Specification (OpenAPI 3.0)

Define API contracts with: info, servers, paths (CRUD endpoints), schemas, responses, security schemes. Use when: API-first development, microservices, third-party integrations.

## Method 3: Requirements Traceability Matrix (RTM)

Link requirements through the full lifecycle:

| Link Type | From → To |
|-----------|-----------|
| Derives | Business Req → Functional Req |
| Implements | Requirement → Code Location |
| Verifies | Test Case → Requirement |
| Depends | Requirement → Requirement |

Includes: Forward Traceability, Backward Traceability, Test Traceability, Coverage Summary, Change Impact Analysis, Verification Status.

## Method 4: Requirements Baseline Management

Version numbering: MAJOR.MINOR.PATCH (Semantic Versioning).

Change Control Process: Change Request → Impact Analysis → CCB Review → Implementation → Documentation.

## Complete Process Checklist

After all 6 phases:
- [ ] Stakeholder list and interview records
- [ ] User personas and journey maps
- [ ] Value sorting matrix (MoSCoW, RICE)
- [ ] User story maps and use case diagrams
- [ ] Priority ranking and release plans
- [ ] Validation report
- [ ] PRD document
- [ ] API specification (if applicable)
- [ ] Requirements Traceability Matrix
- [ ] Requirements baseline with version control

## Exit Criteria

| Criteria | Standard |
|----------|----------|
| PRD Document | Complete and reviewed |
| API Specification | OpenAPI format (if applicable) |
| RTM | All requirements traced, coverage > 80% |
| Baseline | Version established |
| Stakeholder Sign-off | Formal approval obtained |

## Congratulations

Requirements engineering complete. Proceed to design phase with approved PRD, API specifications, and RTM. Remember: requirements specification is the starting point of continuous evolution — maintain good change management.
