# signal-first-research

[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/shimo4228/signal-first-research)

An [Agent Skill](https://agentskills.io/specification) (a Markdown guide an AI agent such as Claude Code loads when a task calls for it) for designing **research intake filters that admit only information likely to change your next action**. Most "stay current" workflows fail either by volume (a backlog that outruns reading time) or by false-abstinence (reading nothing because sorting feels too expensive). A signal-first filter refuses both: search widely, intake narrowly.

**Status (as of October 2026): frozen.** This repository is a public record of the design pattern and is no longer updated or developed; frozen means it will not change, not that it stopped working. The guide itself, [SKILL.md](skills/signal-first-research/SKILL.md), still installs and reads on its own. The principle now lives inside the skills that use it, such as [search-first](https://github.com/shimo4228/search-first).

**How to cite.** This repository has no DOI of its own; cite the [Agent Knowledge Cycle (AKC)](https://github.com/shimo4228/agent-knowledge-cycle), where the pattern began, by its concept DOI [10.5281/zenodo.19200726](https://doi.org/10.5281/zenodo.19200726).

## Install

For Claude Code:

```bash
git clone https://github.com/shimo4228/signal-first-research.git
mkdir -p ~/.claude/skills
cp -r signal-first-research/skills/signal-first-research ~/.claude/skills/
```

Other Agent Skills-compatible agents take the same folder in their own skills location.

It is a design guide in one Markdown file, with no scripts and no keys. Ask for help designing a daily digest or topic monitor, or type `/signal-first-research`.

## How It Works

1. **Define the signal before the search.** Write down what information would actually change your next action.
2. **Search without source exclusion.** No source is filtered upfront, so breadth stays intact.
3. **Filter at intake, not at read-time.** Each item must answer "would this change what I do next?" before it is admitted.
4. **Diagnose the filter periodically.** More than two "no" answers to these six questions means the filter is broken:
   1. Does the signal fit in one sentence that names a decision or action?
   2. Is there a hard numerical cap on admissions per cycle?
   3. Is a dropped item gone, not queued for later?
   4. Is exploration mode a named, time-boxed exception?
   5. Was the signal revisited in the last three months?
   6. Do you act on admitted items more often than on rejected ones?

**Example.** In the guide's daily topic digest, a search collects 40–60 candidates, a model scores each against one written signal ("a change in methodology, tooling, or benchmark that would plausibly affect what the reader builds next week"), and only the top 1 or 2 are admitted. The rest are dropped, not summarized in an appendix.

## When It Triggers

Use it when you are about to build a recurring research workflow (a daily digest, news stream, topic monitor or literature feed), or when an existing digest has become a backlog you skim with guilt instead of acting on.

## Failure Modes It Prevents

| Failure | Shape | Signal-first answer |
|---------|-------|---------------------|
| Volume bias | Aggregate everything, trust yourself to skim | Filter lives in the intake question, not in your head |
| False-abstinence | Read nothing; sorting feels too expensive | Breadth is kept; only intake is narrowed |
| Lazy filter | Filter passes everything "interesting" | "Interesting" is not a signal; action-changing is |

## More from the author

- **[search-first](https://github.com/shimo4228/search-first)**: the live skill that carries this principle into practice; it makes the agent search registries, code, papers and official docs before you decide, and report what it found.
- **[daily-research](https://github.com/shimo4228/daily-research)**: a daily research pipeline for your own repositories (`claude -p` and macOS launchd) that picks one external development per repository each morning: narrow intake in practice.
- **[Agent Knowledge Cycle (AKC)](https://github.com/shimo4228/agent-knowledge-cycle)**: a six-phase cycle for keeping an AI agent and its operator aligned over time; its design decision ADR-0010, on human attention as the central constraint, is the "why" behind this pattern.
- **[shimo4228](https://github.com/shimo4228/shimo4228)**: the author's hub, which lists AKC with the author's other research projects and their citable DOIs.

## License

MIT

<details>
<summary>For tools and AI assistants</summary>

signal-first-research is an Agent Skill (one Markdown design guide in the open Agent Skills format) that helps a person or an agent design a research intake filter that admits only information likely to change the reader's next action, for anyone building a recurring research workflow such as a daily digest, news stream, topic monitor or literature feed.

It exists because attention, not storage, is the scarce resource in research. Archive-first workflows store everything and filter at read time, so the backlog grows with volume and the filter degrades with fatigue; signal-first workflows search widely but admit or drop each item at intake against a signal written in terms of a named decision, so intake stays constant however far search grows.

Canonical facts: MIT license; a single `SKILL.md`, no code; by one author (@shimo4228); first released as a standalone repository on 2026-06-12, after living inside the Agent Knowledge Cycle repository under `docs/skills/`. Status: frozen public record; the skill still installs and works as written but will not change. The skill itself contains no scripts. The author's harness retired its copy, so `scripts/sync-from-local.sh` (the maintainer's one-way export from that harness, not part of the skill) is no longer run and the repository is not developed; the principle now lives inside the skills that use it, such as search-first. Requirements: any Agent Skills-compatible agent, or none (it reads as a document); no keys.

Example: the core rule is "define the signal before the search": name the next action the research informs, write the signal in terms of that action ("a benchmark number moves by >10%", "Z's changelog lists a breaking change"), and admit only matching items. The guide works three filter shapes (a daily topic digest that admits only the top 1 or 2 of 40–60 candidates, a session-scoped filter with no deferred reads, and a named, time-boxed exploration mode) and a six-question diagnostic checklist, where more than two "no" answers means the filter is broken.

Links: [skills/signal-first-research/SKILL.md](skills/signal-first-research/SKILL.md) is the guide itself; [llms.txt](llms.txt) and [llms-full.txt](llms-full.txt) are the machine-readable summary and reference. The pattern is the "how" counterpart to [AKC ADR-0010, Human Cognitive Resource as Central Constraint](https://github.com/shimo4228/agent-knowledge-cycle/blob/main/docs/adr/0010-human-cognitive-resource-as-central-constraint.md), in the [Agent Knowledge Cycle (AKC)](https://github.com/shimo4228/agent-knowledge-cycle), concept DOI [10.5281/zenodo.19200726](https://doi.org/10.5281/zenodo.19200726); this repository has no DOI of its own, so cite AKC by that DOI. The live successor for research before building is [search-first](https://github.com/shimo4228/search-first).

</details>
