# AI Project Governance Starter

> **Vibe Coding Boilerplate** - A complete skeleton for AI-assisted development across multiple IDEs, LLMs, and AI tools.

This repository provides a **comprehensive starting point** for projects that need strong governance for AI-assisted ("vibe") development. It contains templates for documentation, versioning, agent guidance, memory banks, and platform-specific configurations.

## 🚀 Quick Start

```bash
# 1. Copy this directory to your project root
# 2. Read the handbook
cat docs/AGENT_HANDBOOK.md

# 3. Start in Plan Mode - always ask before coding!
```

**Golden Rules:**
- ✅ Always read `docs/AGENT_HANDBOOK.md` first
- ✅ Start in **Plan Mode** - ask intake questions before coding
- ✅ Keep changes small and reviewable
- ❌ Never commit secrets or memory bank files

## 📚 Documentation

| Document | Purpose |
|----------|---------|
| **[Quick Start](docs/QUICK_START.md)** | Get started in 5 minutes |
| **[Vibe Coding Workflow](docs/VIBE_CODING_WORKFLOW.md)** | Complete master guide |
| **[Platform Setup](docs/PLATFORM_SETUP.md)** | IDE/LLM-specific configuration |
| **[Agent Handbook](docs/AGENT_HANDBOOK.md)** | Source of truth for all AI behavior |
| **[Workflow](docs/WORKFLOW.md)** | Phased build process |

## 🔧 Supported Platforms

| Platform | Config File | Features |
|----------|-------------|----------|
| **Claude Code** | `CLAUDE.md` + `.claude/` | Full (subagents, skills, commands, MCP) |
| **Cursor IDE** | `.cursor/rules.md` | Memory bank, partial subagents |
| **GitHub Copilot** | `.github/copilot-instructions.md` | Basic rules |
| **Gemini CLI** | `GEMINI.md` | Separate memory bank |
| **Windsurf** | `.windsurfrules` | Memory bank |
| **Cline** | `.clinerules` | Memory bank, partial subagents |
| **Blackbox AI** | `BLACKBOX.md` | Memory bank |
| **OpenAI Codex** | `CODEX.md` | Memory bank |

## 📁 Repository Structure

```
/
├── docs/                       # Core documentation
│   ├── AGENT_HANDBOOK.md       # ⭐ Source of truth
│   ├── WORKFLOW.md             # Phased build process
│   ├── QUICK_START.md          # 5-minute guide
│   ├── VIBE_CODING_WORKFLOW.md # Complete master guide
│   └── PLATFORM_SETUP.md       # Platform-specific setup
│
├── .claude/                    # Claude Code configuration
│   ├── agents/                 # Subagent definitions
│   ├── commands/               # Slash commands
│   ├── skills/                 # SKILL.md definitions
│   └── settings.json           # Permissions
│
├── agents/                     # Agent persona library
│   └── critical/               # Core agent personas
│
├── Guide On CLAUDE.md/         # CLAUDE.md examples & templates
│   └── CLAUDE.md Collection/   # Framework-specific agents
│
├── skills/                     # Security/pentest skills
│
├── CLAUDE.md                   # Primary Claude config
├── CLAUDE-*.md                 # Domain configs & memory bank
├── GEMINI.md                   # Gemini CLI config
├── CODEX.md                    # OpenAI Codex adapter
├── BLACKBOX.md                 # Blackbox adapter
├── .cursor/rules.md            # Cursor IDE config
├── .windsurfrules              # Windsurf config
├── .clinerules                 # Cline config
├── TECHSTACK.md                # Tech stack documentation
└── AI_GUIDE.md                 # AISP specification
```

## 🧠 Memory Bank System

Create these files to maintain context across sessions:

| File | Purpose |
|------|---------|
| `CLAUDE-activeContext.md` | Current session state & progress |
| `CLAUDE-patterns.md` | Code patterns & conventions |
| `CLAUDE-decisions.md` | Architecture decisions |
| `CLAUDE-troubleshooting.md` | Issues & solutions |

## 🤖 Plan Mode Intake Questions

**Always ask before making changes:**

1. What outcome should the user see when this is done?
2. Which stack is required?
3. Where is the deployment target?
4. What is in scope vs. out of scope?
5. Are there constraints?
6. What are the acceptance criteria?
7. What tests are expected?

## 🔄 Workflow Phases

```
DISCOVERY → PLANNING → IMPLEMENTATION → VERIFICATION → RELEASE
     │           │            │              │            │
     │           │            │              │            └─ CHANGELOG
     │           │            │              └─ Tests, docs
     │           │            └─ Small commits
     │           └─ Get approval
     └─ Ask questions
```

## 📖 Contents

* `README.md` - This overview
* `CHANGELOG.md` - Keep a Changelog format with Unreleased section
* `.env.example` - Sample environment variables
* `.editorconfig` - Consistent formatting rules
* `.gitignore` - Ignores build artifacts, dependencies, and secrets
* `.github/` - GitHub configuration (PR template, Copilot instructions)
* `agents/` - Vendored agent prompts from [wshobson/agents](https://github.com/wshobson/agents)
* `docs/` - Core documentation:
  * `AGENT_HANDBOOK.md` - Single source of truth for agent behavior
  * `AGENT_ROLES.md` - Defines agent responsibilities
  * `WORKFLOW.md` - Phased build process
  * `VERSIONING.md` - Semantic versioning policy
  * `RELEASE_PROCESS.md` - Release steps
  * `QUICK_START.md` - 5-minute getting started
  * `VIBE_CODING_WORKFLOW.md` - Complete master guide
  * `PLATFORM_SETUP.md` - Platform-specific setup

## 🏁 Usage

1. **Copy** this directory to your project root
2. **Customize** `TECHSTACK.md` for your stack
3. **Update** `.env.example` with your variables
4. **Configure** platform-specific files for your IDE
5. **Read** `docs/AGENT_HANDBOOK.md` thoroughly
6. **Create** initial memory bank files

---

> **Note:** To use these templates in a new project, copy this
> directory into the root of your repository and customize the
> contents to reflect your stack (React, Laravel, WordPress, etc.).
