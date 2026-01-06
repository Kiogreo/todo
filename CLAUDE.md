# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Logseq knowledge management repository used for personal note-taking, task tracking, and project documentation. Logseq is an outliner-based knowledge management tool that uses markdown files organized into journals and pages.

## Repository Structure

- `journals/` - Daily journal entries in `YYYY_MM_DD.md` format
- `pages/` - Named pages for specific topics, projects, and documentation
- `logseq/` - Logseq configuration and metadata
  - `config.edn` - Main Logseq configuration file (Clojure EDN format)
  - `.recycle/` - Deleted/archived pages
- `whiteboards/` - Logseq whiteboard diagrams
- `TODO.md` - Main task tracking page with prioritized tasks
- Root-level `.md` files - Active project documentation

## Task Management System

The repository uses Logseq's TODO system with:

- **Workflow**: TODO → DOING → DONE (configured via `:preferred-workflow :todo`)
- **Priorities**: `[#A]` (high), `[#B]` (medium), `[#C]` (low)
- **Time tracking**: `CLOCK:` entries in `:LOGBOOK:` blocks track time spent on tasks
- **Custom renderer**: `{{renderer :todomaster}}` for task visualization
- **Nested tasks**: Tasks organized hierarchically with collapsible sections

### Task Organization in TODO.md

Tasks are organized by category:
- **Main**: Primary development tasks with story IDs (e.g., `ST-12608`)
- **Devops**: Infrastructure and deployment tasks
- **Wiki**: Documentation tasks

## Content Structure Patterns

### Page Linking
- `[[Page Name]]` - Creates bidirectional links between pages
- `[[ST-12608 MULTI PO]]` - Story/ticket references as page links

### Project Documentation Pattern
Project pages (e.g., `ST-12608 MULTI PO.md`) typically contain:
- Demo checklist with `{{renderer :todomaster}}`
- Deployment checklist
- Bug tracking organized by rounds (Round 1, Round 2, Post LIVE)
- Nested task hierarchies with solution details
- Links to external resources (Jira tickets, GitHub PRs)

### Common Metadata Blocks
```
:LOGBOOK:
CLOCK: [YYYY-MM-DD Day HH:MM:SS]--[YYYY-MM-DD Day HH:MM:SS] => HH:MM:SS
:END:
```

## Git Workflow

The repository uses the `logseq-plugin-git` for auto-commits:
- Frequent auto-commits with message format: `[logseq-plugin-git:commit] YYYY-MM-DDTHH:MM:SS.sssZ`
- Manual commits with message: `Auto saved by Logseq`
- Working on branch: `main`

## File Naming Conventions

- Journal files: `YYYY_MM_DD.md` format
- Page files: Use URL-encoded special characters (e.g., `Docker local setup%3A debug issue for HUB Webhook.md` where `%3A` = `:`)
- Story/ticket pages: `ST-{number} {description}.md` format

## Important Notes for Editing

1. **Markdown Syntax**: Logseq uses a specific markdown dialect with outliner syntax
   - Lines starting with `-` or `\t-` are list items (bullets)
   - Indentation creates hierarchy (tabs for nested levels)

2. **Preserve Metadata**: Keep `:LOGBOOK:`, `collapsed::`, and other metadata intact

3. **Task States**: Only use valid states: TODO, DOING, DONE (per config)

4. **Time Tracking**: CLOCK entries should follow exact format shown above

5. **Page References**: Maintain `[[Page Name]]` format for links to work in Logseq

## Related Projects Context

Based on page content, this appears to track work on:
- **SupplyCart**: An e-commerce/procurement platform
- **Multi PO (Purchase Order) Feature**: Major feature with form settings, workflows
- Technologies mentioned: Vue3, InertiaJS, Docker, PHP/Laravel (implied)
