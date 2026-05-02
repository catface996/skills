# Prototype Command: Generate Static HTML Prototype

**Objective**: Generate static HTML prototype from requirements to visualize UI flows and validate user experience.

## Quick Reference

| Aspect | Guideline |
|--------|-----------|
| Input | `requirements.md` (user stories, use cases) |
| Output | `prototype/` directory with static HTML |
| Style | Clean, minimal CSS (no frameworks) |
| Generation | ONE page at a time |

## Strict Rules: Pure Static Files Only

**Required**: Pure HTML + CSS only. Open `index.html` directly in browser (`file://` protocol). All links use relative paths. Inline or local CSS.

**Forbidden**: JavaScript, external CDN/dependencies, server-side technology, build tools, CSS frameworks.

## Pre-Check

- `requirements.md` exists with user stories?
- User flows/use cases documented?
- Spec folder path confirmed?

If check fails: ask user to complete Phase 3 first.

## Output Structure

```
specs/[spec-name]/prototype/
├── index.html          # ONLY index.html in root
├── css/
│   └── style.css       # Shared styles
└── pages/
    ├── [flow-1].html   # ALL other HTML files here
    └── [flow-2].html
```

No HTML files outside `pages/` (except index.html).

## Execution Flow

### Step 1: Analyze Requirements

Read `requirements.md`, extract: UI-related user stories, use case flows, data entities, user actions/interactions.

### Step 2: Plan Pages

Present a page plan table and wait for user confirmation before generating.

### Step 3: Generate Shared CSS

Create `prototype/css/style.css`: clean minimal design, responsive layout, consistent colors, form/button/navigation styles.

### Step 4: Generate Pages (ONE AT A TIME)

For each page:
1. Announce which page and user story
2. Create semantic HTML5 with link to shared CSS, navigation, mock data, interactive states, form inputs
3. Write to file immediately
4. Confirm creation

### Step 5: Generate Index

Create `prototype/index.html`: list all pages, brief descriptions, links.

## HTML Template

```html
<!DOCTYPE html>
<html lang="[language]">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Page Title] - Prototype</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <nav><!-- Navigation --></nav>
    <main><!-- Content --></main>
    <footer><!-- Prototype info --></footer>
</body>
</html>
```

Use realistic mock data (not "Lorem ipsum"), show all UI states, include form validation hints, add comments linking to requirement IDs.
