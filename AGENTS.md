# PJ-LARRY-fo-claude-router

Fork personal de `nixfred/claude-router`: enrutador de modelos para agentes de código (hooks + plugin). Los cambios propios entran por PR a `personal`. La rama `upstream` es un espejo que mantiene el workflow `sync-personal-fork` (ADR 0024 de `robert-flo/fleet`), que cada día rebasa `personal` sobre ella. Nunca push, PR ni issue al upstream.

## Agentes

- **PM: Sura**, el agente principal de `cursor-agent`. Convierte lo que pide Robert en issues `ready-for-agent`, lanza a `wk-fo-claude-router` y a `rv-fo-claude-router` como subagentes y sigue cada issue hasta su PR.
- **`wk-fo-claude-router`** (`.cursor/agents/wk-fo-claude-router.md`): toma un issue y lo lleva a un PR con prueba real.
- **`rv-fo-claude-router`** (`.cursor/agents/rv-fo-claude-router.md`): revisa el PR en solo lectura antes del merge.

## Agent skills

### Issue tracker

GitHub Issues via gh CLI. External PRs are not triaged. See docs/agents/issue-tracker.md.
Prefix issue titles with the issue number and a separator: <number> - <descriptive title>.

### Triage labels

Canonical five-role triage vocabulary (needs-triage, needs-info, ready-for-agent, ready-to-merge, wontfix). See docs/agents/triage-labels.md.

### Domain docs

Single-context repo layout (GLOSSARY.md + docs/adr/ at repo root). See docs/agents/domain.md.
