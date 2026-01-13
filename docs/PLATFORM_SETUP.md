# Platform Setup Guides

> **Detailed setup instructions for each AI coding assistant**

---

## Table of Contents

1. [Claude Code](#1-claude-code)
2. [Cursor IDE](#2-cursor-ide)
3. [GitHub Copilot](#3-github-copilot)
4. [Gemini CLI](#4-gemini-cli)
5. [Windsurf](#5-windsurf)
6. [Cline](#6-cline)
7. [Blackbox AI](#7-blackbox-ai)
8. [OpenAI Codex](#8-openai-codex)
9. [Multi-Platform Setup](#9-multi-platform-setup)

---

## 1. Claude Code

### Overview

Claude Code has the **most complete feature support** for this boilerplate, including subagents, skills, commands, and MCP servers.

### Required Files

```
.claude/
├── settings.json         # Permissions and settings
├── settings.local.json   # Local overrides
├── agents/               # Subagent definitions
│   ├── code-searcher.md
│   ├── memory-bank-synchronizer.md
│   └── ux-design-expert.md
├── commands/             # Slash commands
│   ├── anthropic/
│   ├── architecture/
│   ├── cleanup/
│   ├── promptengineering/
│   ├── refactor/
│   └── security/
├── skills/               # SKILL.md definitions
│   └── claude-docs-consultant/
│       └── SKILL.md
└── mcp/                  # MCP server configs
    └── chrome-devtools.json

CLAUDE.md                 # Primary instructions
CLAUDE-*.md               # Memory bank files (create as needed)
```

### Setup Steps

1. **Verify settings.json**

```jsonc
// .claude/settings.json
{
  "permissions": {
    "allow": [
      "Read(*)",
      "Write(*)",
      "Bash(*)",
      "Grep",
      "Glob",
      "LS"
    ],
    "deny": []
  }
}
```

2. **Create Memory Bank Files**

```bash
# Create initial memory bank
touch CLAUDE-activeContext.md
touch CLAUDE-patterns.md
touch CLAUDE-decisions.md
touch CLAUDE-troubleshooting.md
```

3. **Initialize Active Context**

```markdown
# CLAUDE-activeContext.md

## Current Session
- **Date**: [today's date]
- **Goal**: Initial setup
- **Status**: Ready

## Progress
- [x] Claude Code configured
- [ ] First task pending
```

4. **Verify Subagents**

Test subagent availability:
```
@agent-code-searcher "test search"
@agent-memory-bank-synchronizer "sync check"
```

### Features Available

| Feature | Status | Notes |
|---------|--------|-------|
| Subagents | ✅ Full | All custom agents work |
| Memory Bank | ✅ Full | CLAUDE-*.md files |
| Commands | ✅ Full | /command syntax |
| Skills | ✅ Full | SKILL.md definitions |
| MCP Servers | ✅ Full | Chrome devtools, etc |
| TodoWrite | ✅ Full | Task management |

---

## 2. Cursor IDE

### Overview

Cursor supports CLAUDE.md files and has partial subagent support through its own agent system.

### Required Files

```
.cursor/
└── rules.md              # Cursor-specific rules

CLAUDE.md                 # Also read by Cursor
CLAUDE-*.md               # Memory bank files
```

### Setup Steps

1. **Configure rules.md**

```markdown
# .cursor/rules.md

- Follow `docs/AGENT_HANDBOOK.md`.
- Start in plan mode, ask the required intake questions, and wait for
  answers before making changes.
- Make minimal, well-scoped changes.
- Update docs when user-facing behavior changes.

## Additional Rules
- Always check CLAUDE-activeContext.md for session state
- Reference CLAUDE-patterns.md for code conventions
- Log architectural decisions in CLAUDE-decisions.md
```

2. **Enable CLAUDE.md**

Cursor automatically reads `CLAUDE.md` when present. Ensure it's in the root.

3. **Memory Bank Setup**

Same as Claude Code - create CLAUDE-*.md files.

### Features Available

| Feature | Status | Notes |
|---------|--------|-------|
| Subagents | ⚠️ Partial | Limited to Cursor's system |
| Memory Bank | ✅ Full | CLAUDE-*.md files |
| Commands | ❌ None | Not supported |
| Skills | ❌ None | Not supported |
| MCP Servers | ⚠️ Partial | Depends on Cursor version |

---

## 3. GitHub Copilot

### Overview

GitHub Copilot uses a simpler instruction file but doesn't support memory banks or subagents.

### Required Files

```
.github/
├── copilot-instructions.md    # Copilot rules
└── pull_request_template.md   # PR template
```

### Setup Steps

1. **Configure copilot-instructions.md**

```markdown
# Copilot Instructions

## Ground Rules
- Follow the policies in `docs/AGENT_HANDBOOK.md`.
- Prefer small, reviewable changes.
- Do not commit secrets or credentials.

## Code Quality
- Match existing style and formatting.
- Add tests when behavior changes.
- Update documentation when user-facing behavior changes.

## Plan Mode
Before implementing:
1. Ask clarifying questions about scope
2. Confirm approach for complex work
3. List pros/cons if multiple approaches exist
```

2. **Configure PR Template**

```markdown
## Summary
- 

## Testing
- 

## Checklist
- [ ] Docs updated (if needed)
- [ ] Tests added/updated (if needed)
- [ ] No secrets committed
```

### Features Available

| Feature | Status | Notes |
|---------|--------|-------|
| Subagents | ❌ None | Not supported |
| Memory Bank | ❌ None | Not supported |
| Commands | ❌ None | Not supported |
| Skills | ❌ None | Not supported |
| MCP Servers | ❌ None | Not supported |
| Plan Mode | ⚠️ Partial | Manual prompting required |

---

## 4. Gemini CLI

### Overview

Gemini CLI has its own separate memory bank system using `GEMINI-` prefixed files.

### Required Files

```
GEMINI.md                      # Primary instructions
GEMINI-*.md                    # Memory bank files (separate from Claude)
```

### Setup Steps

1. **Configure GEMINI.md**

The file is already configured. Key points:
- Ignores CLAUDE.md files
- Uses strict instruction adherence
- Has its own memory bank prefix

2. **Create Gemini Memory Bank**

```bash
touch GEMINI-codebase.md
touch GEMINI-activeContext.md
touch GEMINI-patterns.md
touch GEMINI-decisions.md
touch GEMINI-troubleshooting.md
touch GEMINI-config-variables.md
```

3. **Initialize GEMINI-activeContext.md**

```markdown
# Active Context

## Current Session
- **Date**: [today's date]
- **Goal**: Initial setup

## Progress
- [x] Gemini CLI configured
```

### Features Available

| Feature | Status | Notes |
|---------|--------|-------|
| Subagents | ❌ None | Not supported |
| Memory Bank | ✅ Full | GEMINI-*.md files |
| Commands | ❌ None | Not supported |
| Skills | ❌ None | Not supported |
| MCP Servers | ❌ None | Not supported |

### Important Behavioral Differences

- **Strict adherence**: Only does exactly what asked
- **No suggestions**: Won't offer unsolicited advice
- **Scope limitation**: Won't expand on requests
- **Clarification first**: Asks before exceeding scope

---

## 5. Windsurf

### Overview

Windsurf uses a simple rules file that references the main handbook.

### Required Files

```
.windsurfrules              # Windsurf adapter
```

### Setup Steps

1. **Configure .windsurfrules**

```
Follow the policies in docs/AGENT_HANDBOOK.md and docs/WORKFLOW.md.
Start in plan mode, ask the required intake questions, and wait for
answers before making changes.
Keep changes small and focused.

## Memory Bank
- Check CLAUDE-activeContext.md for session state
- Reference CLAUDE-patterns.md for conventions
- Update CLAUDE-decisions.md for architecture choices
```

2. **Use Claude Memory Bank**

Windsurf shares memory bank with Claude using CLAUDE-*.md files.

### Features Available

| Feature | Status | Notes |
|---------|--------|-------|
| Subagents | ❌ None | Not supported |
| Memory Bank | ✅ Full | CLAUDE-*.md files |
| Commands | ❌ None | Not supported |
| Skills | ❌ None | Not supported |
| MCP Servers | ⚠️ Partial | Depends on version |

---

## 6. Cline

### Overview

Cline is configured to read CLAUDE.md directly via its rules file.

### Required Files

```
.clinerules                 # Cline adapter
```

### Setup Steps

1. **Configure .clinerules**

```
# Cline's Memory Bank

Read and use @CLAUDE.md for instruction

## Additional Guidance
- Follow docs/AGENT_HANDBOOK.md
- Start in plan mode
- Ask intake questions before coding
- Use CLAUDE-*.md memory bank files
```

2. **Use Claude Memory Bank**

Cline shares memory bank with Claude using CLAUDE-*.md files.

### Features Available

| Feature | Status | Notes |
|---------|--------|-------|
| Subagents | ⚠️ Partial | Limited support |
| Memory Bank | ✅ Full | CLAUDE-*.md files |
| Commands | ❌ None | Not supported |
| Skills | ❌ None | Not supported |
| MCP Servers | ⚠️ Partial | Depends on version |

---

## 7. Blackbox AI

### Overview

Blackbox uses a minimal adapter file referencing the handbook.

### Required Files

```
BLACKBOX.md                 # Blackbox adapter
```

### Setup Steps

1. **Verify BLACKBOX.md**

```markdown
# Blackbox Adapter

Refer to `docs/AGENT_HANDBOOK.md` for repository policies.
Start in plan mode, ask the required intake questions, and wait for
answers before making changes.
Keep commits small and update documentation when behavior changes.
```

2. **Use Claude Memory Bank**

Blackbox shares memory bank with Claude using CLAUDE-*.md files.

### Features Available

| Feature | Status | Notes |
|---------|--------|-------|
| Subagents | ❌ None | Not supported |
| Memory Bank | ✅ Full | CLAUDE-*.md files |
| Commands | ❌ None | Not supported |
| Skills | ❌ None | Not supported |

---

## 8. OpenAI Codex

### Overview

Codex uses a minimal adapter file similar to Blackbox.

### Required Files

```
CODEX.md                    # Codex adapter
```

### Setup Steps

1. **Verify CODEX.md**

```markdown
# Codex Adapter

This repository follows the policies in `docs/AGENT_HANDBOOK.md`.
Use `docs/WORKFLOW.md` to guide the implementation lifecycle.
Start in plan mode, ask the required intake questions, and wait for
answers before making changes.
```

2. **Use Claude Memory Bank**

Codex shares memory bank with Claude using CLAUDE-*.md files.

### Features Available

| Feature | Status | Notes |
|---------|--------|-------|
| Subagents | ❌ None | Not supported |
| Memory Bank | ✅ Full | CLAUDE-*.md files |
| Commands | ❌ None | Not supported |
| Skills | ❌ None | Not supported |

---

## 9. Multi-Platform Setup

### When Using Multiple AI Tools

If you switch between platforms, follow these practices:

### Shared Configuration

```
docs/
├── AGENT_HANDBOOK.md       # Single source of truth (all platforms)
├── WORKFLOW.md             # Shared workflow (all platforms)
└── VIBE_CODING_WORKFLOW.md # Master reference (all platforms)

CLAUDE-*.md                 # Shared by: Claude, Cursor, Windsurf, Cline, Blackbox, Codex
GEMINI-*.md                 # Gemini-only (separate system)
```

### Gitignore for Memory Banks

```gitignore
# Memory bank files - never commit
CLAUDE-activeContext.md
CLAUDE-temp.md
GEMINI-activeContext.md
GEMINI-temp.md

# Keep patterns and decisions - useful for team
# CLAUDE-patterns.md
# CLAUDE-decisions.md
```

### Session Handoff

When switching platforms mid-session:

1. **Update Active Context**

```markdown
# CLAUDE-activeContext.md

## Platform Handoff
- **Previous**: Claude Code
- **Current**: Cursor
- **Reason**: [why switching]
- **State**: [what was in progress]
```

2. **Sync Memory Banks** (if using Gemini)

Gemini uses separate files, so manually sync important context:

```bash
# Copy key context from Claude to Gemini
cp CLAUDE-patterns.md GEMINI-patterns.md
cp CLAUDE-decisions.md GEMINI-decisions.md
```

### Recommended Primary Platform

| Use Case | Recommended | Why |
|----------|-------------|-----|
| Full AI orchestration | **Claude Code** | Most features |
| IDE-integrated | **Cursor** | Best integration |
| Quick edits | **GitHub Copilot** | Fastest |
| Strict instructions | **Gemini CLI** | No scope creep |
| Lightweight | **Windsurf/Cline** | Simple setup |

---

## Verification Checklist

### After Platform Setup

- [ ] Primary config file exists and is correct
- [ ] Memory bank files created (if supported)
- [ ] Agent handbook accessible
- [ ] Workflow documentation accessible
- [ ] Test a simple task in plan mode
- [ ] Verify intake questions are asked

### Before First Task

- [ ] Read `docs/AGENT_HANDBOOK.md`
- [ ] Read `docs/WORKFLOW.md`
- [ ] Check `CLAUDE-activeContext.md` (if exists)
- [ ] Understand tech stack from `TECHSTACK.md`

---

*For full workflow documentation, see `docs/VIBE_CODING_WORKFLOW.md`*
