# Work System — Production Evidence

A real domain operations advisor system built with Claude Code for enterprise technical consulting. Uses all 6 components at scale. Genericized here — the architecture and patterns are real, domain-specific details replaced.

## Architecture

```
[User query: "troubleshoot connectivity issue for Client X"]
          |
          v
    +-----------+
    | COMMANDS:  |  10 entry points — /troubleshoot, /upgrade,
    | workflow   |  /audit, /mop, /research, + 5 domain-specific
    | triggers   |
    +-----+-----+
          |
    +-----+-----+
    | AGENTS:    |  15 specialized agents
    | domain     |  Core: troubleshooter, upgrade-planner,
    | experts    |  config-analyst, doc-generator, researcher
    |            |  Domain: 6 platform specialists
    |            |  Automation: 2 scripting agents
    +-----+-----+
          |
    +-----+-----+-------+--------+
    |             |               |
    v             v               v
  SKILLS       STATE          CONNECTION
  15 domain    Per-context     MCP/RAG server
  knowledge    project files   80K+ doc chunks
  (up to 518   (topology,      Hybrid search:
  lines each)  inventory,      semantic + keyword
               contacts)
    |             |               |
    +-----+-------+-------+------+
          |
    +-----+-----+
    | HOOKS:     |  File protection
    | 4 active   |  Auto-formatting
    |            |  Security checks
    |            |  Observability tracing
    +-----+-----+
          |
          v
    [Deliverables: Markdown reports, Excel workbooks,
     CLI command blocks, runbooks]
```

## Scale Metrics

| Metric | Count |
|--------|-------|
| Specialized agents | 15 (core, domain, infrastructure, automation) |
| Domain skills | 15 (largest: 518 lines of structured reference) |
| Workflow commands | 10 (each a multi-step pipeline) |
| Doc chunks in RAG | 80,000+ (vendor documentation, hybrid search) |
| Context configurations | Per-client (topology, device inventory, change windows) |
| Deliverable types | 4 (markdown, Excel, CLI blocks, runbooks) |

## Key Patterns

### Per-Context Configuration (State)
Each operational context gets its own configuration file containing:
- Network topology diagram
- Device inventory with versions
- Addressing scheme
- Change window schedule
- Known issues log
- Key contact list

The system loads the relevant context file before any operation. Same agents, same skills, different context → different outputs tailored to that environment.

### Structured Methodology (Flow)
The troubleshooting command enforces a 5-step methodology:
1. **Gather** — collect symptoms, logs, recent changes
2. **Isolate** — narrow scope (layer, device, link, service)
3. **Diagnose** — root cause analysis using gathered data
4. **Resolve** — generate fix commands (human reviews before executing)
5. **Prevent** — document root cause and prevention measures

Each step is explicit. The agent doesn't skip ahead. This is the Gate and Loop patterns from Ch 3 — each step has exit criteria before proceeding.

### Domain Skills (Skill)
Each skill is a structured knowledge document loaded on demand:
- **Evaluation orders** (how the platform processes requests — decision trees)
- **Pattern reference tables** (wildcards, configuration syntax, common setups)
- **Design patterns** (how to structure configurations for different scenarios)
- **Troubleshooting procedures** (step-by-step with expected outputs at each step)

The largest skill is 518 lines. It's not a prompt — it's a reference manual the agent loads and queries as needed.

### Advisor-Only Model (Control)
The system generates recommendations and commands — it never executes directly. Every output is framed as "here's what to do — review before applying." This is a Control pattern: the human is the final Gate before any action takes real-world effect.

## What This Proves for the Book

- **Skills scale**: 15 skills × 15 agents = deep domain coverage without re-explaining context every session
- **State adapts**: Same system handles different environments by swapping context files
- **Connections extend reach**: 80K+ doc chunks mean the system has knowledge beyond what fits in a prompt
- **Flow enforces quality**: The 5-step methodology prevents the "try random things" approach
- **Control prevents harm**: Advisor-only mode is a system-level Hook — nothing executes without human review
