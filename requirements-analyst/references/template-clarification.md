# Clarification Output Template

**Output File**: `specs/[feature-name]/clarification.md`

```markdown
# Clarification Log: [Feature Name]

**Feature**: [feature-name]
**Session Date**: YYYY-MM-DD
**Total Questions**: [N]
**Status**: In Progress | Completed

---

## Q1: [Question Title]

**Category**: Functional Scope / Domain & Data / Interaction & UX / Non-Functional / Integration / Edge Cases / Terminology

**Question**: [Complete question text]

**Options Presented**:
- **A**: [Option A]
- **B**: [Option B]
- **C**: [Option C]
- **Other**: Custom answer

**Recommended**: Option [X] - [Reason]

**User's Choice**: [Choice]

**Resolution**: [How applied]

**Applied To**: [Section in requirements.md]

---

## Summary

| # | Question | Category | Choice | Applied To |
|---|----------|----------|--------|------------|
| 1 | [Brief] | [Category] | [Choice] | [Section] |

---

## Coverage Summary

| Category | Status | Notes |
|----------|--------|-------|
| **Functional Scope** | Resolved / Clear / Deferred | [Note] |
| **Domain & Data** | Resolved / Clear / Deferred | [Note] |
| **Interaction & UX** | Resolved / Clear / Deferred | [Note] |
| **Non-Functional** | Resolved / Clear / Deferred | [Note] |
| **Integration** | Resolved / Clear / Deferred | [Note] |
| **Edge Cases** | Resolved / Clear / Deferred | [Note] |
| **Terminology** | Resolved / Clear / Deferred | [Note] |

**Status Legend**: Resolved (was ambiguous, now clarified), Clear (already sufficient), Deferred (non-blocking)

---

## Impact on Analysis Document

### Sections Modified

| Section | Change Description |
|---------|-------------------|
| [Section] | [Change] |

### User Stories Updated

| Story ID | Original | Updated |
|----------|----------|---------|
| US-XXX | [Original] | [Updated] |

### New Requirements Added

| Req ID | Description | Source |
|--------|-------------|--------|
| REQ-XXX | [New requirement] | Q[N] |

---

## Deferred Items

| Item | Category | Reason | When to Resolve |
|------|----------|--------|-----------------|
| [Item] | [Category] | [Why] | Implementation / Design |

---

## Assumptions Documented

| ID | Assumption | Related Req | Risk if Wrong | Validated |
|----|------------|-------------|---------------|-----------|
| ASM-001 | [Assumption] | REQ-XXX | [Risk] | Yes/No |

---

## Next Steps Available

| Option | Action | When to Choose |
|--------|--------|----------------|
| **A** | Clarify (Continue) | Deferred items need resolution |
| **B** | Analyze (Re-analyze) | Significant changes |
| **C** | Validate (Proceed) | All critical ambiguities resolved |

**Recommendation**: [A/B/C] — [Reason]
```
