# signal-first-research

[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/shimo4228/signal-first-research) [![GitMCP](https://img.shields.io/endpoint?url=https://gitmcp.io/badge/shimo4228/signal-first-research)](https://gitmcp.io/shimo4228/signal-first-research) [![View Code Wiki](https://assets.codewiki.google/readme-badge/static.svg)](https://codewiki.google/github.com/shimo4228/signal-first-research)

An [Agent Skill](https://agentskills.io/specification) for designing **research intake filters that admit only information likely to change your next action**. Most "stay current" workflows fail either by volume (a guilt queue that outruns reading time) or by false-abstinence (reading nothing because sorting feels too expensive). A signal-first filter refuses both: search widely, intake narrowly.

## Install

### Claude Code

```bash
# Copy into your global skills directory
cp -r skills/signal-first-research ~/.claude/skills/signal-first-research
```

### SkillsMP

```bash
/skills add shimo4228/signal-first-research
```

## How It Works

1. **Define the signal before the search** — write down what information would actually change your next action
2. **Search without source exclusion** — no source is filtered upfront; breadth stays intact
3. **Filter at intake, not at read-time** — each item must answer "would this change what I do next?" before it is admitted
4. **Diagnose the filter periodically** — a checklist distinguishes a healthy filter from one that has quietly broken (lazy passthrough, topic creep, guilt backlog)

## When It Triggers

- You are about to build a recurring research workflow — daily digest, news stream, topic monitor, literature feed
- The default question "what should I read?" keeps producing too much
- An existing digest has become a backlog you skim with guilt instead of acting on

## Failure Modes It Prevents

| Failure | Shape | Signal-first answer |
|---------|-------|---------------------|
| Volume bias | Aggregate everything, trust yourself to skim | Filter lives in the intake question, not in your head |
| False-abstinence | Read nothing; sorting feels too expensive | Breadth is kept; only intake is narrowed |
| Lazy filter | Filter passes everything "interesting" | "Interesting" is not a signal; action-changing is |

## Syncing from the harness

The canonical copy of this skill lives in the author's live Claude Code harness. This repository is a one-way publication mirror:

```bash
scripts/sync-from-local.sh --dry-run   # report differences only
scripts/sync-from-local.sh             # apply to working tree (never commits)
```

## About this skill

This skill is a design-pattern skill from the [Agent Knowledge Cycle (AKC)](https://github.com/shimo4228/agent-knowledge-cycle) research line — a Zenodo-citable six-phase bidirectional growth loop ([DOI 10.5281/zenodo.19200726](https://doi.org/10.5281/zenodo.19200726)) for sustaining intent alignment between an AI agent and its operator over time. It is the "how" counterpart to [AKC ADR-0010 Human Cognitive Resource as Central Constraint](https://github.com/shimo4228/agent-knowledge-cycle/blob/main/docs/adr/0010-human-cognitive-resource-as-central-constraint.md). AKC is one of three research lines by [@shimo4228](https://github.com/shimo4228), alongside [Contemplative Agent](https://github.com/shimo4228/contemplative-agent) ([DOI 10.5281/zenodo.19212118](https://doi.org/10.5281/zenodo.19212118)) — autonomous agents grounded in four contemplative axioms — and [Agent Attribution Practice (AAP)](https://github.com/shimo4228/agent-attribution-practice) ([DOI 10.5281/zenodo.19652013](https://doi.org/10.5281/zenodo.19652013)) — harness-neutral ADRs on accountability distribution.

## License

MIT
