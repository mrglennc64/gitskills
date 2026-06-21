# Attribution & licenses

This repository **vendors** (copies) skills from upstream open-source projects. All credit goes to the
original authors. Each upstream license is preserved in [`licenses/`](licenses/).

| Vendored into | Source repo | Commit | License |
|---|---|---|---|
| `code-agent/skills/` | [mattpocock/skills](https://github.com/mattpocock/skills) | `6eeb81b` | MIT |
| `code-agent/skills/` | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | `17214a2` | MIT |
| `marketing-agent/skills/` | [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | `8bfcdff` | MIT |
| `reference/claude-fable-5.md` | [asgeirtj/system_prompts_leaks](https://github.com/asgeirtj/system_prompts_leaks) | `Anthropic/claude-fable-5.md` | CC0-1.0 |

## Tools referenced (not vendored)

- [NVIDIA/SkillSpector](https://github.com/NVIDIA/SkillSpector) — Apache-2.0 — skill security scanner; see [`security/scan-report.md`](security/scan-report.md).
- [chopratejas/headroom](https://github.com/chopratejas/headroom) — Apache-2.0 — LLM context compressor; optional infra, not a skill (see README "Phase 4").

## Dedup note

`code-agent` drops two upstream skills to avoid redundancy:
- `mattpocock` **`tdd`** — superseded by `addyosmani` **`test-driven-development`**.
- `mattpocock` **`setup-matt-pocock-skills`** — an installer specific to the upstream repo.

To prefer mattpocock's TDD instead, restore its folder from upstream and remove
`code-agent/skills/test-driven-development/`.
