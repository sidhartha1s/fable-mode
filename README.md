# fable-mode

A Claude Code skill that loads **Claude Fable 5's working discipline** into any session — so Opus, Sonnet, or any other model executes layered tasks the way Fable does: scope → evidence → adversarial reasoning → verification → calibrated reporting.

Fable 5 was Anthropic's Mythos-class model available on subscription plans through mid-2026. A skill file can't transfer its raw intelligence, but it can transfer *how it works* — the five-gate task loop, the standing habits, and the handoff signature its done-reports follow.

## What's inside

- **`SKILL.md`** — the skill (v3). Five gates, standing habits, gate-skip smells, and a handoff-signature report format. Includes the runtime judgments distilled from Fable's agentic layer: provenance-ranked evidence, subagent prompt-armoring, scope self-arrest, collapse-scope-not-standards, claim-vs-artifact separation, harness-noise discrimination.
- **`fable-insights.md`** — the raw distillation notes the v2/v3 improvements were built from (leaked consumer prompt + observed agentic discipline).

## Install

```bash
mkdir -p ~/.claude/skills/fable-mode
curl -o ~/.claude/skills/fable-mode/SKILL.md https://raw.githubusercontent.com/sidhartha1s/fable-mode/main/SKILL.md
```

Or clone the repo into `~/.claude/skills/`.

## Use

Triggers proactively on any layered task (multi-step builds, debugging, research with claims), or say:

> fable mode · think like Fable · use the Fable method · slow down and do this right · think this through first

## Credits

- Original five-gate skill concept: **Nate Herk**
- v2/v3 improvements: distilled with Claude Fable 5 itself, from its agentic operating discipline, before subscription sign-off (2026-07)

## License

MIT
