# Validation Output Template

**Output File**: `specs/[feature-name]/validation.md`

```markdown
# Validation Report: [Feature Name]

**Feature**: [feature-name]
**Date**: YYYY-MM-DD
**Status**: In Progress | Completed

---

## Executive Summary

[2-3 sentences summarizing validation outcome]

**Overall Status**: ✅ Validated / ⚠️ Conditional / ❌ Failed

---

## 1. Validation Dimension Summary

| Dimension | Status | Score | Critical Issues | Notes |
|-----------|--------|-------|-----------------|-------|
| **Authenticity** | ✅/⚠️/❌ | [%] | [Count] | [Note] |
| **Completeness** | ✅/⚠️/❌ | [%] | [Count] | [Note] |
| **Consistency** | ✅/⚠️/❌ | [%] | [Count] | [Note] |
| **Feasibility** | ✅/⚠️/❌ | [Rating] | [Count] | [Note] |
| **Verifiability** | ✅/⚠️/❌ | [%] | [Count] | [Note] |

---

## 1.1 Validation Radar Chart

\`\`\`mermaid
%%{init: {'radar': {'max': 100, 'graticule': 'polygon', 'ticks': 5}}}%%
radar-beta
    title "Requirements Validation Score"
    axis auth["Authenticity"], comp["Completeness"], cons["Consistency"], feas["Feasibility"], veri["Verifiability"]
    curve score["Score"]{auth: 85, comp: 92, cons: 95, feas: 78, veri: 88}
    curve threshold["Threshold (80%)"]{auth: 80, comp: 80, cons: 80, feas: 80, veri: 80}
\`\`\`

### Score Progress Bars

| Dimension | Score | Visual | Status |
|-----------|-------|--------|--------|
| **Authenticity** | [X]% | ████████░░ | ✅/⚠️/❌ |
| **Completeness** | [X]% | █████████░ | ✅/⚠️/❌ |

### Key Insight

> [2-3 sentences on strengths, weaknesses, focus areas]

---

## 2. Authenticity Validation

### Score: [X]% - [Status]

**Formula**: (Verified + Confirmed) / (Total × 2) × 100

### Positive Findings

| Req ID | Origin | Evidence | Confirmed |
|--------|--------|----------|-----------|
| REQ-001 | User Interview | [Evidence] | ✅ |

### Negative Findings (Red Flags)

| Req ID | Red Flag | Impact | Action |
|--------|----------|--------|--------|
| REQ-003 | No user evidence | May build unwanted feature | Research |

### Verdict

> [2-3 sentences explaining score]

---

## 3. Completeness Validation

### Score: [X]% - [Status]

| Category | Total | Specified | Weight | Score | Target |
|----------|-------|-----------|--------|-------|--------|
| Functional | [N] | [N] | 30% | [%] | ≥95% |
| Data | [N] | [N] | 20% | [%] | ≥95% |
| Flows | [N] | [N] | 20% | [%] | ≥90% |

### Gaps

| Gap ID | Category | Missing Item | Severity | Action |
|--------|----------|--------------|----------|--------|
| GAP-001 | Error | API timeout handling | Major | Define flow |

---

## 4. Consistency Validation

### Score: [X]% - [Status]

**Formula**: (Passed + Resolved) / Total × 100

### Conflicts

| ID | Type | Req A | Req B | Description | Status |
|----|------|-------|-------|-------------|--------|
| CON-001 | Logic | REQ-001 | REQ-005 | [Conflict] | Resolved |

---

## 5. Feasibility Validation

### Overall: [Rating] - [Status]

| Sub-Dimension | Rating | Weight | Key Factor |
|---------------|--------|--------|------------|
| Technical | High/Med/Low | 30% | [Factor] |
| Economic | Viable/Marginal | 25% | ROI: [X]% |
| Operational | High/Med/Low | 20% | [Factor] |
| Schedule | Achievable/Risk | 15% | Gap: [N] days |
| Compliance | Compliant/Gap | 10% | [Factor] |

---

## 6. Verifiability Validation

### Score: [X]% - [Status]

### Vague Terms Found

| Term | Found In | Replacement |
|------|----------|-------------|
| "fast" | REQ-004 | "< 2s response" |

### GWT Coverage

| Req ID | Happy Path | Error | Edge Cases | Status |
|--------|------------|-------|------------|--------|
| REQ-001 | ✅ | ✅ (3) | ✅ (2) | Complete |

---

## 7. Multi-Role Validation

| Req ID | PM | RA | SA | SE | TE | Overall |
|--------|----|----|----|----|-----|---------|
| REQ-001 | ✅ | ✅ | ⚠️ | ✅ | ✅ | ⚠️ |

---

## 8. Outstanding Issues

| ID | Dimension | Severity | Description | Owner | Status |
|----|-----------|----------|-------------|-------|--------|
| V-001 | [Dim] | Critical | [Desc] | [Name] | Open |

---

## 9. Sign-Off

| Role | Name | Decision | Date |
|------|------|----------|------|
| Product Owner | [Name] | Approved/Rejected | [Date] |

---

## Next Steps

| Option | Action | When |
|--------|--------|------|
| **A** | Specify | All pass, no critical issues |
| **B** | Validate | Issues remain |
| **C** | Clarify | Ambiguities found |
| **D** | Analyze | Major gaps |

**Recommendation**: [A/B/C/D] — [Reason]
```
