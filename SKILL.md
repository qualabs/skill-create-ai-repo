---
name: init-project
description: Project initializer for AI agentic development. Use when setting up a new project for AI agent collaboration, creating plan structure, or generating an AGENTS.md.
---

# Init Project - AI Agentic Development Starter

Interactive skill to initialize projects optimized for AI agent-assisted development. Creates folder structure, base documentation, and planning workflows.

## Workflow

Create a todo list for this workflow and work through each task sequentially.

### 1. Gather Project Information

Use `AskUserQuestion` to collect project details:

```
Describe your project:
1. What type of project is it? (web app, API, CLI, library, mobile, etc.)
2. What is the main purpose?
3. What language/framework will you use?
4. Do you have any documentation, URLs, or reference files to include? (optional)
```

Store the responses for use in generating the AGENTS.md.

### 2. Detect Repository Context

Analyze the current directory to detect:
- Existing project (package.json, pyproject.toml, Cargo.toml, go.mod, etc.)
- Current folder structure
- Whether AGENTS.md or CLAUDE.md already exists

```bash
ls -la
```

Check for project manifests to detect the stack.

### 3. Create Plans Folder

Create the plans directory based on context:

**If `docs/` folder exists:**
```bash
mkdir -p docs/plans
```

**If no `docs/` folder:**
```bash
mkdir -p .plans
```

Copy the templates from this skill's `templates/` folder:
- `plans-readme.md` → `[plans-folder]/README.md`
- `plan-template.md` → `[plans-folder]/_template.md`

### 4. Suggest Essential Skills

Ask the user which skills they'd like to enable:

```
Based on your project, I suggest these complementary skills:

- code-review: Automated code review with checklist
- clean-code: SOLID principles, refactoring, code smells detection

Which would you like to configure? (select one or more, or "none")
```

### 5. Process External Documentation (Optional)

If the user provided URLs or files:

1. **For URLs:** Use `WebFetch` to retrieve relevant content
2. **For files:** Use `Read` to extract key information
3. **Summarize** and add to the Reference Documentation section of AGENTS.md

### 6. Generate AGENTS.md

Create `AGENTS.md` in the project root using the template from `templates/AGENTS.md.template`.

Fill in the following sections based on gathered information:

1. **Project Description** - From user's answers in step 1
2. **Reference Documentation** - URLs/files provided (if any)
3. **Plans Section** - Location of plans folder, testing requirements
4. **Auto-Retrospective Section** - Instructions for continuous improvement
5. **Active Skills** - Skills the user chose to enable
6. **Change History** - Initial entry with current date

### 7. Show Summary

Present a summary to the user:

```
## Project Initialized

### Files Created:
- AGENTS.md - Main documentation for AI agents
- [plans-folder]/README.md - Plans guide
- [plans-folder]/_template.md - Template for new plans

### Skills Configured:
- [list of active skills, or "none"]

### Next Steps:
1. Review AGENTS.md and adjust as needed
2. Create your first plan in the plans folder
3. Start developing!

### Tip:
After completing significant implementations, check the auto-retrospective
section to keep AGENTS.md updated with project learnings.
```

---

## Notes

- The skill is fully interactive - it asks before assuming
- Adapts to existing or new projects
- Plans folder location is flexible (.plans/ or docs/plans/)
- AGENTS.md includes self-improvement mechanism
- Only suggests essential skills (code-review, clean-code)
