# Project Pulse agent team

Mona's Project Pulse dashboard will be built by a team of custom agents orchestrated through GitHub Copilot CLI in a Codespace.

| Agent | Model | Responsibility | Definition |
| --- | --- | --- | --- |
| Orchestrator | Claude Opus 4.7 (copilot) | Coordinates the specialists, turns the plan into safe phases, assigns non-overlapping file scopes, verifies the integrated result, and reports blockers and outcomes. | `.github/agents/orchestrator.agent.md` |
| Planner | Claude Opus 4.7 (copilot) | Researches the repository and produces an implementation plan covering file ownership, dependencies, parallel work, edge cases, and validation. | `.github/agents/planner.agent.md` |
| Coder | GPT-5.5 (copilot) | Implements the dashboard structure and behavior, creates assigned runtime support, and validates that the result is deterministic and runnable. | `.github/agents/coder.agent.md` |
| Designer | Gemini 3.1 Pro (copilot) | Defines and implements the dashboard's UI and UX, including accessibility, information hierarchy, responsive behavior, and polished visual styling. | `.github/agents/designer.agent.md` |

## How the team will work together

1. The Orchestrator asks the Planner to research Project Pulse and define ordered implementation phases, file ownership, dependencies, and validation expectations.
2. The Orchestrator converts the plan into scoped assignments. Independent Coder and Designer work can run in parallel only when their file ownership does not overlap; dependent or overlapping work runs sequentially.
3. The Coder builds the assigned application structure, data, behavior, and launch support. The Designer creates the assigned visual and interaction experience while following the Project Pulse design expectations.
4. The Orchestrator reviews the combined work, checks that the files and experience fit together, coordinates validation, and reports the final result or any blockers.
