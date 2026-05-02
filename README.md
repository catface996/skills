# Skills

A collection of Claude Code skills for professional workflows.

## Skills Index

| Skill | Description |
|-------|-------------|
| [requirements-analyst](./requirements-analyst/) | 6-phase requirements engineering workflow |

---

## requirements-analyst

Professional requirements engineering skill with two expert roles — **Product Manager** (user value, product direction) and **Requirements Analyst** (detailed, executable requirement documents).

### Workflow

```
Discovery → Value Sorting → Analysis → Clarification → Validation → Specification
```

| Phase | Focus | Output |
|-------|-------|--------|
| 1. Discovery | Stakeholder analysis, personas, journey maps, competitive analysis | `discovery.md` |
| 2. Value Sorting | MoSCoW classification, RICE scoring, release planning | `sort.md` |
| 3. Analysis | User stories, use cases, domain modeling, NFR analysis | `requirements.md` + `data-model.md` |
| 4. Clarification | Ambiguity elimination through targeted questioning | `clarification.md` |
| 5. Validation | 5-dimension validation (Authenticity, Completeness, Consistency, Feasibility, Verifiability) | `validation.md` |
| 6. Specification | PRD, OpenAPI spec, Requirements Traceability Matrix | `prd.md` + `api.yaml` + `rtm.md` |

Also supports:
- **Reverse** — Extract requirements from existing codebases
- **Prototype** — Generate static HTML prototypes from requirements
- **Simplified 3-phase workflow** — Understanding → Clarification → Validation (for small features)

### Features

- Auto-detects language from user input (Chinese / English)
- Diagrams over text — uses Mermaid UML for all visual output
- Incremental delivery — writes deliverables section by section
- Configurable output directory (defaults to `specs/`)

### File Structure

```
requirements-analyst/
├── SKILL.md                              # Main skill definition (routing + workflow)
└── references/
    ├── phase1-discovery.md               # Stakeholder interviews, personas, journey maps
    ├── phase2-sort.md                    # MoSCoW, RICE, value-cost matrix
    ├── phase3-analysis.md                # User stories, use cases, NFR, domain modeling
    ├── phase4-clarification.md           # Ambiguity taxonomy, sequential questioning
    ├── phase5-validation.md              # 5-dimension validation, multi-role review
    ├── phase6-specification.md           # PRD, OpenAPI, RTM, baseline management
    ├── command-reverse.md                # Code-to-requirements extraction
    ├── command-prototype.md              # Static HTML prototype generation
    ├── diagram-standards.md              # Mermaid/UML diagram conventions
    ├── multi-role-validation.md          # 5-role validation perspectives
    ├── template-discovery.md             # Phase 1 output template
    ├── template-sort.md                  # Phase 2 output template
    ├── template-analysis.md              # Phase 3 output template
    ├── template-data-model.md            # Data model output template
    ├── template-clarification.md         # Phase 4 output template
    ├── template-validation.md            # Phase 5 output template
    ├── template-prd.md                   # PRD output template
    ├── template-openapi.md               # OpenAPI spec template
    └── template-rtm.md                   # Traceability matrix template
```

### Usage

Install the skill in Claude Code, then trigger it with phrases like:

- "help me figure out what to build"
- "write requirements for my project"
- "create a PRD"
- "analyze this codebase and extract requirements"
- "需求分析"
- "逆向工程"
- "生成原型"

---

## Adding New Skills

Create a new directory at the repo root with the skill name:

```
skills/
├── README.md
├── requirements-analyst/
│   ├── SKILL.md
│   └── references/
└── your-new-skill/
    ├── SKILL.md
    └── references/
```

Each skill must have a `SKILL.md` with YAML frontmatter (`name`, `description`) as entry point.
