# gitskills

Two curated, security-scanned **Agent Skill** bundles for Claude Code, vendored from public repos:

| Agent | Skills | Source | Intended model |
|---|---|---|---|
| **[`code-agent/`](code-agent/)** | 45 software-engineering skills | mattpocock/skills + addyosmani/agent-skills | **Fable 5** (`claude-fable-5`) |
| **[`marketing-agent/`](marketing-agent/)** | 45 marketing skills | coreyhaines31/marketingskills | any |

Every skill is the standard `SKILL.md` + YAML-frontmatter format Claude Code loads natively. All three
sources are MIT; see [`NOTICE.md`](NOTICE.md). A pre-install security scan is in
[`security/scan-report.md`](security/scan-report.md) (result: **PASS**).

## The "Fable 5 code skills"

There is no separate "Fable 5 skills" project — **Fable 5 is the model** (`claude-fable-5`). The code
skills in `code-agent/` are what you run **on** Fable 5. The leaked Fable 5 system prompt is included
as read-only reference at [`reference/claude-fable-5.md`](reference/claude-fable-5.md) (CC0); it is
**not** a skill and is not installed.

## Install

Skills load from `~/.claude/skills/` (global) or `<project>/.claude/skills/` (project). Pick one:

### Option A — copy the skills (simplest)

```bash
# Code agent, global:
cp -r code-agent/skills/*      ~/.claude/skills/
# Marketing agent, global:
cp -r marketing-agent/skills/* ~/.claude/skills/
```

On Windows (PowerShell):

```powershell
Copy-Item code-agent\skills\*      "$env:USERPROFILE\.claude\skills\" -Recurse
Copy-Item marketing-agent\skills\* "$env:USERPROFILE\.claude\skills\" -Recurse
```

Restart Claude Code, then type `/` to confirm the skills appear.

### Option B — install as plugins

Each agent dir is a self-contained plugin (`.claude-plugin/plugin.json` + `skills/`). Add this repo as
a plugin marketplace and install `code-agent` and/or `marketing-agent` via `/plugin`.

## Run the code agent on Fable 5

Skills are model-agnostic; "Fable 5 code agent" = these skills + the Fable 5 model. After installing
`code-agent`:

```
/model claude-fable-5
```

(or set `"model": "claude-fable-5"` in your settings). Optionally lift coding patterns you like from
`reference/claude-fable-5.md` into a project `CLAUDE.md`.

## What's in each agent

- **code-agent** — define (interview-me, idea-refine, spec/domain modeling), plan (planning-and-task-breakdown,
  to-prd, to-issues), build (implement, prototype, incremental-implementation, TDD, frontend-ui-engineering,
  api-and-interface-design, codebase-design), verify (diagnosing-bugs, debugging-and-error-recovery,
  browser-testing-with-devtools), review (code-review-and-quality, code-simplification, security-and-hardening,
  performance-optimization), ship (git-workflow, ci-cd, docs-and-adrs, observability, deprecation-and-migration),
  plus guardrails (git-guardrails, setup-pre-commit) and meta (writing-great-skills, using-agent-skills).
- **marketing-agent** — CRO, copywriting, SEO/AI-SEO, ads/ad-creative, analytics, churn/retention, pricing,
  launch, cold-email, content-strategy, and ~35 more.

## Repos considered but not vendored

- **NVIDIA/SkillSpector** (Apache-2.0) — security scanner; used as the install gate, not a skill.
- **chopratejas/headroom** (Apache-2.0) — LLM context compressor; optional infrastructure (a proxy/MCP),
  wire it only if you hit context limits.
- **asgeirtj/system_prompts_leaks** (CC0) — prompt archive; only `claude-fable-5.md` was pulled as reference.

## Re-running the real scanner

When a compatible toolchain/Docker is available:

```bash
skillspector scan ./code-agent/skills/      --format markdown --output security/skillspector-code.md
skillspector scan ./marketing-agent/skills/ --format markdown --output security/skillspector-marketing.md
```
