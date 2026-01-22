# ⚠️ CRITICAL - READ THIS FIRST ⚠️

## 🚨 THIS IS **NOT** A CLAUDE CODE PROJECT 🚨

### Framework Identification

**Primary System**: **OpenCode CLI**  
**Framework**: **OpenAgent Framework** (OpenAgentsControl)  
**NOT**: ~~Claude Code~~

---

## 🛑 HARD RULES - VIOLATION IS UNACCEPTABLE

### Rule 1: Directory Structure
❌ **NEVER** reference or create `.Claude/` directories  
✅ **ALWAYS** use `.opencode/` for agent system files

❌ **WRONG**: `.Claude/agent/`, `.Claude/context/`, `.Claude/command/`  
✅ **CORRECT**: `.opencode/agent/`, `.opencode/context/`, `.opencode/command/`

### Rule 2: Import Paths
❌ **WRONG**: `import { tool } from "@Claude-ai/plugin/tool"`  
✅ **CORRECT**: `import { tool } from "@opencode-ai/plugin/tool"`

### Rule 3: CLI Commands
❌ **WRONG**: `Claude --agent openagent`  
✅ **CORRECT**: `opencode --agent openagent`

### Rule 4: Agent References
❌ **WRONG**: Referring to "Claude Code agents", "Claude framework"  
✅ **CORRECT**: "OpenCode agents", "OpenAgent framework"

### Rule 5: Documentation
❌ **WRONG**: Applying Claude Code conventions and patterns  
✅ **CORRECT**: Following OpenAgent Framework patterns from AGENTS.md

---

## 📁 Correct Project Structure

```
.opencode/              # OpenCode CLI system directory
├── agent/              # AI agents (NOT .Claude/agent/)
│   ├── core/          # Core system agents (openagent, opencoder)
│   ├── meta/          # Meta-level agents (system-builder)
│   └── subagents/     # Specialized helpers
├── command/           # Slash commands
├── context/           # Knowledge base
│   ├── core/         # Essential patterns
│   └── project/      # Project-specific patterns
├── plugin/           # Optional extensions
└── tool/             # Optional tools

pages/                # Markdown documentation/notes
journals/             # Daily journals (Logseq)
tasks/                # Task management files
.input/               # Input files for specialized workflows
.output/              # Output files from specialized workflows
```

---

## 🔍 How to Identify This Project

**Check these indicators:**
1. Directory name: `.opencode/` exists (NOT `.Claude/`)
2. AGENTS.md line 3-4: Explicitly states "NOT a Claude Code repository"
3. Import statements: Use `@opencode-ai/` namespace
4. CLI commands: Use `opencode` command
5. Agent references: Mention "OpenAgent Framework"

---

## 📚 Source of Truth

**Primary Documentation**: `AGENTS.md`

Read lines 1-10 of AGENTS.md FIRST before working on any file:

```markdown
# AGENTS.md - OpenAgent Framework Guide

⚠️ **CRITICAL: This is NOT a Claude Code repository!**  
This repository uses **OpenCode CLI** with the **OpenAgent Framework** (OpenAgentsControl).  
Do NOT apply Claude Code-specific patterns, structures, or conventions to this repository.
```

---

## ⚡ Quick Check Before ANY Operation

Before reading, writing, or suggesting ANY change, ask yourself:

1. ❓ Am I using `.opencode/` paths? (NOT `.Claude/`)
2. ❓ Am I referencing OpenCode CLI? (NOT Claude Code)
3. ❓ Am I following OpenAgent Framework patterns?
4. ❓ Have I read AGENTS.md to understand the project?

If you answered "No" to ANY question above, **STOP** and correct your approach.

---

## 🎯 When Testing or Creating New Components

### For Agent Files
❌ Path: `.Claude/agent/subagents/my-agent.md`  
✅ Path: `.opencode/agent/subagents/my-agent.md`

### For Context Files
❌ Path: `.Claude/context/core/standards.md`  
✅ Path: `.opencode/context/core/standards.md`

### For Commands
❌ Path: `.Claude/command/my-command.md`  
✅ Path: `.opencode/command/my-command.md`

### For Specialized Workflows (like AI Brainstormer)
✅ Input files: `.input/` directory  
✅ Output files: `.output/` directory  
✅ Context: `.input/context/[workflow-name]/`  
✅ Agent files: May be in `.input/` OR `.opencode/agent/subagents/`

---

## 🚫 Common Mistakes to Avoid

1. **Assuming Claude Code conventions** - This is OpenAgent Framework
2. **Using wrong directory names** - `.Claude/` does not exist here
3. **Wrong import paths** - Use `@opencode-ai/` not `@Claude-ai/`
4. **Wrong CLI commands** - Use `opencode` not `Claude`
5. **Ignoring AGENTS.md** - It's the primary source of truth

---

## ✅ Validation Checklist

Before submitting ANY work, verify:

- [ ] No references to `.Claude/` directories
- [ ] No references to "Claude Code" (except when contrasting)
- [ ] All paths use `.opencode/` or project-specific directories
- [ ] All imports use `@opencode-ai/` namespace
- [ ] All CLI commands use `opencode` command
- [ ] Documentation follows OpenAgent Framework patterns
- [ ] AGENTS.md has been read and understood

---

## 📞 If You're Confused

1. **STOP** what you're doing
2. **READ** AGENTS.md lines 1-100
3. **CHECK** existing directory structure with glob
4. **ASK** the user for clarification
5. **NEVER** assume Claude Code conventions apply

---

**Remember**: This is **OpenCode CLI + OpenAgent Framework**, NOT Claude Code.

Confusion on this point will result in unusable code and wasted effort.

---

*This file exists to prevent repeated mistakes. Do not delete.*  
*Last updated: 2026-01-22*
