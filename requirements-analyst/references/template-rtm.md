# Requirements Traceability Matrix (RTM) Template

**Output File**: `specs/[feature-name]/rtm.md`

```markdown
# Requirements Traceability Matrix

## 1. Document Information

| Field | Value |
|-------|-------|
| **Project** | [Project Name] |
| **Version** | v1.0.0 |
| **Last Updated** | [Date] |
| **Owner** | [Name] |

---

## 2. Traceability Matrix

### 2.1 Forward Traceability (Requirements → Implementation)

| Req ID | Requirement | Priority | Design Ref | Code Ref | Test Case | Status |
|--------|-------------|----------|------------|----------|-----------|--------|
| REQ-001 | [Brief] | Must | DES-001 | `src/module/file.ts:L50` | TC-001 | Implemented |

### 2.2 Backward Traceability (Implementation → Requirements)

| Component | Code Location | Implements | Test Coverage |
|-----------|---------------|------------|---------------|
| UserService | `src/services/user.ts` | REQ-001, REQ-002 | TC-001~TC-003 |

### 2.3 Test Traceability

| Test Case ID | Test Name | Requirements | Type | Status |
|--------------|-----------|-------------|------|--------|
| TC-001 | User registration | REQ-001 | Functional | Pass |

---

## 3. Coverage Summary

### 3.1 Requirements Coverage

| Category | Total | Designed | Implemented | Tested | Verified |
|----------|-------|----------|-------------|--------|----------|
| Functional | [N] | [N] (%) | [N] (%) | [N] (%) | [N] (%) |
| Non-Functional | [N] | [N] (%) | [N] (%) | [N] (%) | [N] (%) |

### 3.2 Gap Analysis

| Gap Type | Count | Requirements | Action |
|----------|-------|--------------|--------|
| No Design | 0 | - | - |
| No Implementation | [N] | [List] | [Plan] |
| No Test Cases | [N] | [List] | [Plan] |

---

## 4. Dependency Chain

| Req ID | Depends On | Depended By |
|--------|------------|-------------|
| REQ-001 | - | REQ-002, REQ-003 |

---

## 5. Change Impact Analysis

| If Changed | Affects Design | Affects Code | Affects Tests | Risk |
|------------|---------------|--------------|---------------|------|
| REQ-001 | DES-001 | 5 files | 8 tests | High |

### Change Log

| Date | Req ID | Change | Description | Impact |
|------|--------|--------|-------------|--------|
| [Date] | REQ-005 | Modified | Updated criteria | Low |

---

## 6. Verification Status

| Req ID | Method | Verified By | Date | Result |
|--------|--------|-------------|------|--------|
| REQ-001 | Test + Demo | QA Team | [Date] | Pass |

### Sign-off

| Stakeholder | Role | Requirements | Date | Status |
|-------------|------|--------------|------|--------|
| [Name] | Product Owner | All Functional | [Date] | Approved |

---

## 7. Maintenance

### Update Triggers

| Event | Action |
|-------|--------|
| New requirement | Add row to forward traceability |
| Requirement modified | Update all linked items |
| Code committed | Update Code Ref column |
| Test added | Update Test Case column |

### Review Schedule

| Type | Frequency | Participants |
|------|-----------|--------------|
| Coverage Review | Weekly | Dev + QA |
| Gap Analysis | Bi-weekly | PM + Tech Lead |
| Full RTM Review | Per Release | All Stakeholders |
```
