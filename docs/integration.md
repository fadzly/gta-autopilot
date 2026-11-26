# PS5 MCP integration decision

Reviewed 26 November 2026. Verification consisted of inspecting public upstream documentation and the selected server's Python tool declarations. Hardware results below are attributed to their authors.

| Candidate | What the upstream evidence establishes | Decision |
| --- | --- | --- |
| [Jeff-Kazzee/ps5-agent-remote](https://github.com/Jeff-Kazzee/ps5-agent-remote) | Its [MCP server](https://github.com/Jeff-Kazzee/ps5-agent-remote/blob/main/mcp_server.py) defines ps5_look, ps5_press and ps5_play. The last accepts timed steps and a requested frame count. The README describes Windows 10/11 x64, a native bridge and fake-server tests. Clean-machine setup and second-console pairing remain open upstream. | First Windows trial. Local timing and intermediate frames directly address controller timing between model calls. |
| [khodossss/ps5-remoteplay-mcp](https://github.com/khodossss/ps5-remoteplay-mcp) | The [published 0.2.2 description](https://pypi.org/project/ps5-remoteplay-mcp/0.2.2/) and repository README document a stock-console Remote Play daemon and a recorded racing-game setup menu demonstration. The README identifies Windows 11 testing, unverified in-game analog controls and untested macOS. | Alternative for a separate macOS feasibility trial. Measure input and release before attempting a driving objective. |
| [Darkatek7/ps5-mcp](https://github.com/Darkatek7/ps5-mcp) | Upstream documents screen and controller tools on a modified console. | Different hardware prerequisite from the stock-console target. |

Reviewed Git blob IDs: Jeff-Kazzee README `fa65aaad668515f51073c27697e928a2c9f4d2a1`, MCP source `f0ef5c75ed4c1c595009887c00bdbd49d6525817`, khodossss README `0671a67e46ae06b5351e18ad3ca46c08ed23d7d9`. Pin an installable commit in each run report.

Use a separately installed bridge behind a small adapter. Keep upstream binaries and dependencies outside this MIT project. The first decision to revisit is whether capture age and action latency allow steering corrections within a measured in-game time window.
