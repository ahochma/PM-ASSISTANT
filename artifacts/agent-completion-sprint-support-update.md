# Agent Creation Complete! 🎉

## Agent Summary

- **Name:** Sprint Reporter
- **Type:** Simple
- **Purpose:** Produce support-team updates from sprint CSV (template: Headline [Product name], Description, Asana link)
- **Status:** Ready for installation

## File Locations

- **Agent Config:** `sprint-support-update-writer.agent.yaml`
- **Plan (reference):** `agent-plan-sprint-support-update.md`

## Installation

Package your agent as a standalone module with `module.yaml` containing `unitary: true`.
See: [BMAD Custom Content Installation Guide](https://github.com/bmad-code-org/BMAD-METHOD/blob/main/docs/modules/bmb-bmad-builder/custom-content-installation.md#standalone-content-agents-workflows-tasks-tools-templates-prompts)

## Quick Start

1. Create a module folder (e.g. `my-custom-stuff`)
2. Add `module.yaml` with `unitary: true`
3. Place agent in `agents/sprint-support-update-writer/sprint-support-update-writer.agent.yaml`
4. Install via BMAD installer (new projects: prompt for local modules; existing: "Modify BMAD Installation")

## First Use

1. Invoke the agent (e.g. via BMAD/Cursor command for your agent).
2. Run **[SU] Generate support-team update from sprint CSV**.
3. Provide your sprint CSV and short summary; receive the formatted support update.
