# fable-mode

A Claude Code skill that loads Claude Fable 5's working discipline into any session, so Opus, Sonnet, or any other model executes layered tasks the way Fable does.

## What it does

- Fable 5 was Anthropic's Mythos-class model available on subscription plans through mid-2026. This skill cannot transfer its raw intelligence, but it transfers how it works: scope, then evidence, then adversarial reasoning, then verification, then calibrated reporting.
- Defines a five-gate task loop: a gate must pass before the next opens, and when a task stalls or surprises you, you name which gate you are at and re-run it.
- Includes runtime judgments distilled from Fable's agentic layer: provenance-ranked evidence, subagent prompt-armoring, scope self-arrest, collapse-scope-not-standards, claim-vs-artifact separation, and harness-noise discrimination.
- Triggers proactively on any layered task (multi-step builds, debugging, research with claims), or on the phrases "fable mode", "think like Fable", "use the Fable skill", "use the Fable method", "work like Fable", "slow down and do this right", or "think this through first".

## Gate 1: scope before work

- Define done in one or two sentences: what artifact exists at the end, what must be true of it, and how you will check that it is true. If you cannot write the check, you do not understand the task yet.
- Check standing rules first (CLAUDE.md, skills, memory), and read the relevant SKILL.md before producing anything it covers.
- Separate known from assumed, and name the one to three load-bearing unknowns explicitly.
- Look up any entity you do not confidently recognize (product, model, version, API, technique) before reasoning about it.
- Enumerate every ask in a multi-part message before acting, since dictated messages often bundle several instructions.

## Gate 2: evidence before reasoning

- Never design from memory of what a file, API, or dataset probably looks like; open it.
- Rank evidence by provenance, per fact: disk beats live tool output beats memory files beats session summaries beats training data. When two tiers disagree, the higher tier wins and the lower one gets flagged as stale.
- When inputs arrive malformed (wrong paths, empty args, garbled data), recover ground truth from disk before failing or guessing.
- Attack the load-bearing unknowns first, with the cheapest probe: a 30-second read of the real data beats an hour of building on a guess.

## Install

```bash
mkdir -p ~/.claude/skills/fable-mode
curl -o ~/.claude/skills/fable-mode/SKILL.md https://raw.githubusercontent.com/sidhartha1s/fable-mode/main/SKILL.md
```

Or clone the repo into `~/.claude/skills/`.

## Usage

Fires proactively on layered tasks: multi-step builds, debugging where the first theory might be wrong, research that produces claims, anything needing verification before handoff. Also fires on the trigger phrases above. For a one-file edit or a simple lookup, skip the gates and just do the work.

## Layout

- `SKILL.md`: the skill itself (v3), five gates, standing habits, gate-skip smells, and a handoff-signature report format.
- `fable-insights.md`: the raw distillation notes the v2/v3 improvements were built from.

## Notes

- A hard task is one where the first idea might be wrong. Gates 3 through 5 cover adversarial reasoning, verification, and calibrated reporting; only Gates 1 and 2 are excerpted above.
