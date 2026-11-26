# GTA Autopilot

GTA Autopilot aims to let Claude Code or Codex play GTA VI story mode on a PS5, recover from failed checkpoints and continue across missions. This repository currently contains the design, research and contribution workflow. There is no runnable autopilot release.

| Capability | Evidence today |
| --- | --- |
| Screen capture and timed controller input | Upstream interfaces reviewed. Project hardware trial pending. |
| Claude Code and Codex sessions | Proposed. Each client needs a separate smoke test. |
| Mission completion, automatic retries and continuous play | Proposed. Zero project-validated missions. |

Start with the [development tracker](TRACKER.md) to pick a task. The first experiment measures how quickly a stock PS5 shows the effect of a controller input. A menu screenshot alone cannot establish whether an agent can drive in real time.

- [Roadmap and acceptance criteria](ROADMAP.md)
- [PS5 MCP research and integration decision](docs/integration.md)
- [Runtime design](docs/architecture.md) and [validation guide](docs/validation.md)
- [Contributing](CONTRIBUTING.md), [Claude Code](CLAUDE.md) and [Codex](AGENTS.md)

GitHub holds the design history, run reports, issues and reviewed changes. Original project material is distributed under the [MIT license](LICENSE).
