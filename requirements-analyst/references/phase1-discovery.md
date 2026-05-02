# Phase 1: Requirements Discovery

**Objective**: Discover and elicit user requirements from scratch, understand business context and user pain points.
**Time Allocation**: 40% of total effort
**Role**: Professional Requirements Analyst

## Quick Reference

| Method | Focus | Output | Critical? |
|--------|-------|--------|-----------|
| Stakeholder Analysis | Power-Interest Matrix | Stakeholder list + Interview plans | Yes |
| User Personas | 3-5 typical personas | Detailed persona documents | Yes |
| Journey Mapping | Core business flows | Visual journey maps | Yes |
| Field Observation | Actual usage scenarios | Pain points list | Optional |
| Competitive Analysis | 2-3 competitors | Feature comparison matrix | Yes |
| Requirements Collection | All raw requirements | Preliminary requirements list | Yes |

**Minimum Viable Discovery**: Stakeholder Interviews + User Personas + Journey Map + Competitive Analysis

## Output

**File**: `specs/[feature-name]/discovery.md`
**Template**: Read `references/template-discovery.md`

## Pre-Check

| Check | Requirement |
|-------|-------------|
| Project Authorization | Formal approval to start |
| Stakeholder Access | Can contact key stakeholders |
| Time Allocation | At least 40% of total time |

If any check fails: STOP and resolve before proceeding.

## Tasks

1. **Identify Stakeholders**: Use power-interest matrix for systematic identification
2. **Create User Personas**: 3-5 detailed personas for each key role
3. **Map User Journeys**: Visualize complete user journeys
4. **Conduct Competitive Analysis**: Analyze 2-3 major competitors
5. **Uncover Pain Points**: Discover unexpressed implicit needs

---

## Method 1: Stakeholder Identification and Interviews

### Power-Interest Matrix

```
            High Interest
                |
    +-----------+-----------+
    |  Manage   |   Engage  |  <- Key Players (High Priority)
    |  Closely  |  Closely  |
----+-----------+-----------+----
    |  Monitor  |   Keep    |  <- Secondary (Lower Priority)
    |           | Informed  |
    +-----------+-----------+
                |
            Low Interest
       Low Power    High Power
```

### Interview Plan Template

```markdown
## Interview Plan

**Interview Subject**: [Name/Role]
**Interview Time**: [Date Time]
**Interview Location**: [Location/Online]
**Interview Objectives**: [What to understand from this interview]

**Question List**:
1. What are your main responsibilities related to this project?
2. What problems do you face in your daily work?
3. What would an ideal solution look like?
4. What constraints should we be aware of?
5. Who else should we talk to?
```

### Interview Techniques

- Use open-ended questions to elicit requirements
- Use "5 Whys" to find root causes
- Record user quotes verbatim
- Observe non-verbal cues
- Follow up on vague answers

---

## Method 2: User Personas

### Persona Template

```markdown
## User Persona: [Name]

### Demographics
- **Age**: [Range]
- **Role/Occupation**: [Title]
- **Technical Proficiency**: Novice/Intermediate/Expert
- **Company Size**: Startup/SMB/Enterprise

### Goals & Motivations
- Primary: [Main goal]
- Secondary: [Supporting goals]

### Pain Points & Frustrations
- [Pain point 1 with severity: High/Medium/Low]
- [Pain point 2 with severity]
- [Pain point 3 with severity]

### Behaviors & Preferences
- [How they currently solve the problem]
- [Tools they use]
- [Communication preferences]

### Usage Context
- **When**: [Time/Frequency of use]
- **Where**: [Environment - office, mobile, etc.]
- **How**: [Devices, access methods]

### Quote
> "[Verbatim quote from interviews that captures their perspective]"

### Key Requirements (inferred)
1. [Requirement derived from this persona]
2. [Requirement derived from this persona]
```

---

## Method 3: User Journey Map

### Journey Map Structure

```markdown
## User Journey: [Journey Name]

**Persona**: [Which persona]
**Scenario**: [What they're trying to accomplish]

| Stage | Discovery | Consideration | Use | Completion |
|-------|-----------|---------------|-----|------------|
| **Actions** | [What user does] | [What user does] | [What user does] | [What user does] |
| **Thoughts** | [What user thinks] | [What user thinks] | [What user thinks] | [What user thinks] |
| **Emotions** | [Rating] | [Rating] | [Rating] | [Rating] |
| **Pain Points** | [Issues faced] | [Issues faced] | [Issues faced] | [Issues faced] |
| **Opportunities** | [Improvement ideas] | [Improvement ideas] | [Improvement ideas] | [Improvement ideas] |
| **Touchpoints** | [Systems/people] | [Systems/people] | [Systems/people] | [Systems/people] |
```

Map each journey with: Stages, Actions, Thoughts, Emotions, Pain Points, Opportunities, and Touchpoints.

---

## Method 4: Competitive Analysis

### Feature Comparison Matrix

```markdown
## Competitive Analysis Report

### Competitors Analyzed
1. [Competitor A] - [Market position]
2. [Competitor B] - [Market position]

### Feature Comparison Matrix

| Feature | Our Product | Competitor A | Competitor B |
|---------|-------------|--------------|--------------|
| [Feature 1] | Planned | Yes | No |
| [Feature 2] | Planned | No | Yes |
```

### SWOT Analysis (Per Competitor)

```markdown
**Competitor A**:
- Strengths: [List]
- Weaknesses: [List]
- Opportunities for us: [How we can differentiate]
- Threats: [What they do better]
```

### Differentiation Opportunities

1. [Gap in market we can fill]
2. [Underserved user need]
3. [Better approach to existing feature]

---

## Exit Criteria

| Item | Standard |
|------|----------|
| Stakeholder List | All key stakeholders identified (>= 5 interviews) |
| User Personas | 3-5 typical personas created |
| Journey Map | Core business process mapped |
| Raw Requirements | Preliminary list compiled (>= 20 items) |
| Competitive Analysis | 1-2 competitors analyzed |
| Pain Points | Core pain points identified (>= 5 items) |

## Next Step

Phase 2: Value Sorting — Use MoSCoW and RICE models to prioritize requirements.
