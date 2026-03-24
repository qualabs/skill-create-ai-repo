# init-project

A Claude Code skill for initializing projects with AI agentic development best practices.

## What it does

This skill helps you set up new projects (or configure existing ones) for optimal AI agent collaboration:

1. **Gathers project info** - Asks about your project type, purpose, and stack
2. **Creates plans folder** - Sets up a structured location for implementation plans
3. **Generates AGENTS.md** - Creates documentation that guides AI agents working on your project
4. **Suggests skills** - Recommends complementary skills (code-review, clean-code)

## Installation

### Option 1: Global installation (recommended)

Copy this repository to your Claude Code skills folder:

```bash
cp -r skill-create-ai-repo ~/.claude/skills/init-project
```

### Option 2: Project-specific installation

Copy to a specific project's `.claude/skills/` folder:

```bash
cp -r skill-create-ai-repo /path/to/project/.claude/skills/init-project
```

## Usage

Once installed, run the skill in any project directory:

```
/init-project
```

The skill will interactively guide you through the setup process.

## What gets created

After running the skill, your project will have:

```
your-project/
├── AGENTS.md              # Main documentation for AI agents
└── .plans/                # (or docs/plans/)
    ├── README.md          # Plans folder guide
    └── _template.md       # Template for new plans
```

## AGENTS.md Features

The generated AGENTS.md includes:

- **Project Description** - Overview of your project
- **Guidelines for AI Agents** - Development principles and standards
- **Plans Section** - Where to store plans, testing requirements
- **Auto-Retrospective** - Self-improvement process after implementations
- **Change History** - Track updates to the document

## Templates

The `templates/` folder contains:

| File | Purpose |
|------|--------|
| `AGENTS.md.template` | Base template for AGENTS.md generation |
| `plan-template.md` | Template for implementation plans |
| `plans-readme.md` | README for the plans folder |

## License

MIT
