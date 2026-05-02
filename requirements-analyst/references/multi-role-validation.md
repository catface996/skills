# Multi-Role Validation Perspectives

Requirements must be validated from 5 role perspectives to ensure completeness and feasibility.

## Product Manager (PM)

**Focus**: Business value and user alignment

| Dimension | Key Questions |
|-----------|---------------|
| Business Value | Clear ROI? Delivers business value? |
| User Need | Solves a real user problem? Pain point validated? |
| Market Fit | How does this compare to competitors? |
| Strategic Alignment | Aligns with product vision and roadmap? |
| Priority Justification | MoSCoW/RICE justified by business metrics? |
| Success Metrics | Defined and measurable? |

**Checklist**: Business case justified, user personas validated, feature aligns with strategy, success metrics measurable, stakeholder buy-in obtained.

## Requirements Analyst (RA)

**Focus**: Completeness, clarity, and traceability

| Dimension | Key Questions |
|-----------|---------------|
| Completeness | All functional and non-functional requirements captured? |
| Clarity | Each requirement unambiguous with one interpretation? |
| Consistency | Any conflicts between requirements? |
| Traceability | Each requirement traces to business goals? |
| Boundary Conditions | Edge cases and error conditions defined? |
| Dependencies | All dependencies identified? |

**Checklist**: Unique IDs, no ambiguous terms, main/alternate/exception flows documented, boundary conditions stated, traceability matrix complete, no conflicts.

## Software Architect (SA)

**Focus**: Technical feasibility and system impact

| Dimension | Key Questions |
|-----------|---------------|
| Technical Feasibility | Implementable with current stack? |
| Architecture Impact | How does this affect existing architecture? |
| Scalability | Will it scale to expected load? |
| Security | Authentication? Authorization? Data protection? |
| Performance | Requirements realistic and measurable? |
| Integration | Systems to integrate? APIs defined? |

**Checklist**: NFRs quantified, architecture constraints identified, integration points documented, no impossible requirements, security OWASP-aligned.

## Software Engineer (SE)

**Focus**: Implementation clarity and effort estimation

| Dimension | Key Questions |
|-----------|---------------|
| Implementation Clarity | Clear how to implement? |
| Effort Estimation | Can effort be estimated accurately? |
| Error Handling | What happens when things go wrong? |
| Data Validation | Input validation rules? |
| Backward Compatibility | Does this break existing functionality? |

**Checklist**: Implementation approach clear, data models defined, error handling specified, input validation documented, backward compatibility addressed.

## Test Engineer (TE)

**Focus**: Testability and quality assurance

| Dimension | Key Questions |
|-----------|---------------|
| Testability | Can this be tested? How? |
| Acceptance Criteria | GWT format and verifiable? |
| Test Coverage | What test types needed? |
| Edge Cases | Boundary conditions testable? |
| Automation Feasibility | Can tests be automated? |

**Checklist**: Every requirement has GWT acceptance criteria, happy path defined, 2-3 error scenarios per requirement, edge cases identified, test data requirements documented.

## Cross-Role Conflict Resolution

| Conflict Type | Resolution Approach |
|---------------|---------------------|
| PM vs SA (wants vs feasibility) | Negotiate scope or timeline |
| RA vs SE (definition vs clarity) | Clarify implementation details |
| SA vs TE (design vs testability) | Adjust design for testability |
| PM vs TE (speed vs quality) | Balance scope, time, quality |

## Validation Report Format

```markdown
### Requirement: [REQ-XXX]

| Role | Status | Issues | Recommendations |
|------|--------|--------|-----------------|
| PM   | ✅/⚠️/❌ | [Issues] | [Recommendations] |
| RA   | ✅/⚠️/❌ | [Issues] | [Recommendations] |
| SA   | ✅/⚠️/❌ | [Issues] | [Recommendations] |
| SE   | ✅/⚠️/❌ | [Issues] | [Recommendations] |
| TE   | ✅/⚠️/❌ | [Issues] | [Recommendations] |

Overall Status: [APPROVED / NEEDS REVISION / REJECTED]
```
