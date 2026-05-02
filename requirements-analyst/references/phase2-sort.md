# Phase 2: Value Sorting

**Objective**: Prioritize requirements and develop release plans.
**Time Allocation**: 10% of total effort
**Role**: Professional Requirements Analyst

## Quick Reference

| Method | Focus | Output |
|--------|-------|--------|
| MoSCoW | Categorical priority | MUST/SHOULD/COULD/WONT list |
| RICE Scoring | Quantitative ranking | Scored priority list |
| Value-Cost Matrix | Trade-off visualization | Quadrant placement |
| Release Planning | MVP + versions | Release roadmap |

**MUST requirements must not exceed 30% of total.**

## Output

**File**: `specs/[feature-name]/sort.md`
**Template**: Read `references/template-sort.md`

## Pre-Check

- Phase 1 completed? Discovery.md exists with stakeholder analysis?
- Inputs available? Raw requirements list ready?
- Unclear items identified? Requirements with unclear business value flagged?

If any check fails: STOP and return to Phase 1.

---

## Method 1: MoSCoW Classification

| Category | Definition | Typical % |
|----------|------------|-----------|
| Must Have | Cannot launch without | <= 30% |
| Should Have | Important, can workaround | 20-30% |
| Could Have | Nice to have | 20-30% |
| Won't Have | Not this release | 10-20% |

### Decision Questions

| Question | If Yes |
|----------|--------|
| Does the product fail without it? | MUST |
| Legal/regulatory requirement? | MUST |
| Workaround possible? | SHOULD (not MUST) |
| Will users be significantly impacted? | SHOULD |
| "Delight" feature? | COULD |
| Can wait for next release? | COULD or WON'T |

### MoSCoW Template

```markdown
## MoSCoW Classification: [Release/Version]

### MUST Have (<= 30% of total)
| Req ID | Requirement | Justification |
|--------|-------------|---------------|
| REQ-001 | [Description] | [Why it's MUST] |

**MUST Count**: X / Y total = Z% (must be <= 30%)

### SHOULD Have
| Req ID | Requirement | Impact if Deferred |
|--------|-------------|-------------------|
| REQ-003 | [Description] | [Impact] |

### COULD Have
| Req ID | Requirement | Value Add |
|--------|-------------|-----------|
| REQ-005 | [Description] | [Benefit] |

### WON'T Have (This Release)
| Req ID | Requirement | Reason for Exclusion |
|--------|-------------|---------------------|
| REQ-006 | [Description] | [Why not now] |
```

---

## Method 2: RICE Scoring

```
RICE Score = (Reach x Impact x Confidence) / Effort
```

### RICE Factors

| Factor | Scale | How to Estimate |
|--------|-------|-----------------|
| Reach | Users affected per quarter | Analytics, user research |
| Impact | 0.25 (Minimal) to 3 (Massive) | See scale guide below |
| Confidence | 0-100% | Data-backed(100%) to Gut(20%) |
| Effort | Person-months | Engineering estimate |

### Impact Scale Guide

| Score | Level | Description | Example |
|-------|-------|-------------|---------|
| 3 | Massive | Fundamental improvement | Core workflow optimization |
| 2 | High | Significant improvement | Major pain point solved |
| 1 | Medium | Noticeable improvement | Useful enhancement |
| 0.5 | Low | Minor improvement | Small convenience |
| 0.25 | Minimal | Barely noticeable | Micro optimization |

### RICE Scoring Example

| Req ID | Reach | Impact | Confidence | Effort | RICE Score | Rank |
|--------|-------|--------|------------|--------|------------|------|
| REQ-001 | 10,000 | 2 | 80% | 2 | 8,000 | 1 |
| REQ-002 | 5,000 | 3 | 90% | 3 | 4,500 | 2 |
| REQ-003 | 8,000 | 1 | 70% | 1 | 5,600 | 3 |

Calculation: REQ-001: (10,000 x 2 x 0.80) / 2 = 8,000

---

## Method 3: Value-Cost Matrix

| Quadrant | Strategy | Action |
|----------|----------|--------|
| P0 (High Value, Low Cost) | Do First | Quick Win — prioritize immediately |
| P1 (High Value, High Cost) | Plan Carefully | Strategic — worth investment but plan |
| P2 (Low Value, Low Cost) | If Time Permits | Fill-in — easy add-ons |
| P3 (Low Value, High Cost) | Deprioritize | Avoid — usually not worth it |

### Scoring Criteria

- **Value**: Business impact (1-10)
- **Cost**: Development effort (1-10, where 10 = highest cost)

| Req ID | Value (1-10) | Cost (1-10) | Quadrant | Action |
|--------|--------------|-------------|----------|--------|
| REQ-001 | 9 | 3 | P0 (Quick Win) | Do First |
| REQ-002 | 8 | 8 | P1 (Strategic) | Plan Carefully |
| REQ-003 | 3 | 2 | P2 (Fill-in) | If Time Permits |
| REQ-004 | 4 | 9 | P3 (Avoid) | Deprioritize |

---

## Method 4: Release Planning

### MVP Definition

MVP Criteria:
- Solves the core user problem
- Technically feasible within timeline
- Provides basis for learning/iteration
- Contains only MUST requirements

```markdown
## MVP Scope
| Req ID | Requirement | Why MVP |
|--------|-------------|---------|
| REQ-001 | [Description] | [Core to value proposition] |

### Not in MVP (Explicitly Excluded)
| Req ID | Requirement | Deferred To |
|--------|-------------|-------------|
| REQ-003 | [Description] | V1.1 |
```

### Release Roadmap

Define subsequent versions with: Theme, Scope, Dependencies, Success Metrics.

```markdown
### MVP (Target: [Date])
**Theme**: Core functionality
**Scope**: [Feature list]
**Success Criteria**: [Metrics]

### Version 1.1 (Target: [Date])
**Theme**: Enhanced usability
**Dependencies**: MVP complete

### Version 2.0 (Target: [Date])
**Theme**: Scale and advanced features
**Dependencies**: V1.1 complete
```

---

## Stakeholder Alignment

### Priority Review Session

```markdown
## Priority Review Meeting

**Date**: [Date]
**Attendees**: [List]

### Decisions Made
1. [Decision 1]

### Conflicts Resolved
| Issue | Resolution | Rationale |
|-------|------------|-----------|
| [Conflict] | [How resolved] | [Why] |

### Approvals
- [ ] Product Owner
- [ ] Technical Lead
- [ ] Business Stakeholder
```

---

## Exit Criteria

| Criteria | Standard |
|----------|----------|
| MoSCoW Classification | 100% classified, MUST <= 30% |
| RICE Scoring | Core requirements scored |
| Priority List | Ranked, no dependency conflicts |
| Release Plan | MVP and versions defined |
| Stakeholder Approval | Priorities confirmed |

## Next Step

Phase 3: Analysis — Deep analysis with user stories, use cases, domain modeling, and NFR specification.
