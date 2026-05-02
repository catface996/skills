# Reverse Command: Extract Requirements from Existing Code

**Objective**: Reverse engineer an existing codebase to extract and document requirements for legacy or undocumented projects.
**Role**: Professional Requirements Analyst with Code Analysis Skills

## When to Use

- Onboarding to an existing project without documentation
- Creating requirements documentation for undocumented projects
- Preparing for major refactoring or modernization
- Generating requirements baseline before enhancement

## Prerequisites

**Required**: Existing codebase with read access to source files, config files, and package manifests.
**Helpful**: README, git history, running application, stakeholder access.

## Execution Steps

| Step | Focus | Output |
|------|-------|--------|
| 1. Project Discovery | Scan codebase structure | Project overview |
| 2. Tech Stack Analysis | Identify technologies | Technology inventory |
| 3. Architecture Analysis | Map structure & patterns | Architecture summary |
| 4. Product Context | Understand purpose & users | Product context summary |
| 5. Feature Extraction | Identify business features | Feature inventory |
| 6. Requirements Synthesis | Convert to requirements | Requirements list |
| 7. User Review | Validate with user | Confirmed requirements |

## Output

**File**: `specs/[spec-name]/reverse.md`

After completion, user can proceed to Phase 2 (Sort) or Phase 3 (Analysis).

## Operating Constraints

- **Non-destructive**: Only reads and analyzes, never modifies existing code
- **User confirmation**: All extracted requirements require user review
- **Evidence-based**: Every requirement must trace to specific code evidence
- **Mermaid first**: Flows, processes, sequences, relationships must use Mermaid diagrams

## Step 1: Project Discovery

Scan: root directory, project boundaries, monorepo vs single project, configuration files, entry points, git history (age, contributors, active areas).

## Step 2: Technology Stack Analysis

Parse package manifests, identify frameworks, testing tools, build tools, CI/CD, infrastructure (Docker, cloud configs), database configurations.

## Step 3: Architecture Analysis

Map folder hierarchy, identify patterns (MVC, Clean Architecture, etc.), detect module boundaries, shared code, naming conventions, API patterns, data access patterns, dependency graph. Extract data models from ORM models → generate `erDiagram`.

## Step 4: Product Context

Parse README/docs, analyze route handlers/controllers, extract business logic from service layers, check environment variables/feature flags, localization files, permission configs.

## Step 5: Feature Extraction

Scan HTTP endpoints, WebSocket handlers, background jobs, event handlers. Analyze service layer code, validation rules, business workflows, authorization rules. Map UI components to features. Detect TODO/FIXME/HACK comments, deprecated code, technical debt.

**Output format**:
```
| Feature ID | Feature Name | Code Location | Evidence |
|------------|--------------|---------------|----------|
| F-001 | User Login | src/auth/login.ts:45 | POST /api/login |
```

## Step 6: Requirements Synthesis

For each feature: identify user need, extract functional behavior, document constraints/validations, identify NFR aspects.

Format each as: REQ-XXX with Source, Type, Description, Evidence (file, function, behavior), Acceptance Criteria (inferred), Notes (mark uncertain items with `[INFERRED]`).

## Step 7: User Review

Present findings with summary statistics, then offer:
- A) Review each requirement before saving
- B) Save all and review later
- C) Ask questions about specific findings
- D) Re-analyze specific areas

## Analysis Guidelines

- Quote specific files and line numbers
- Mark uncertain conclusions with `[INFERRED]`
- Distinguish facts from assumptions
- Focus on primary code, skip node_modules/build artifacts
- Respect .gitignore patterns

## Exit Criteria

| Item | Standard |
|------|----------|
| Project Overview | Scope and tech stack documented |
| Architecture Diagram | At least one Mermaid diagram |
| Feature Inventory | All major features with evidence |
| Requirements List | ≥10 items for typical project |
| Technical Debt | TODO/FIXME/deprecated catalogued |
| User Validation | User has reviewed findings |
