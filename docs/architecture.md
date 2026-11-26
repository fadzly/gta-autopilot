# Proposed runtime

The operator starts story mode and selects the objective. Claude Code or Codex reads a fresh observation and chooses a short action. A local supervisor owns the controller and the run journal. The Remote Play bridge owns pairing, input timing and frame capture.

| Adapter operation | Candidate mapping | Supervisor contract |
| --- | --- | --- |
| observe | ps5_look | Return frame ID, monotonic receive time and capture timestamp if available. Unknown frame age is explicit. |
| act | ps5_play | Accept action ID, expected observation ID and a bounded sequence of button, stick and trigger states. End in neutral. |
| stop | Local cancellation plus backend neutralization | Reject new work, cancel queued inputs and test release on disconnect before claiming stop support. |

Use one controller writer. Give the model high-level decisions and schedule time-sensitive inputs on the host clock. Measure action-to-visible-change latency before choosing sequence duration. A late observation, lost connection, unknown dialog or manual takeover suspends input.

Record run ID, mission, checkpoint, attempt, action ID, observation IDs, outcome and remaining budget after each transition. Persist action intent before dispatch. If the process restarts with an unacknowledged intent, observe the scene again before issuing another command.

A mission definition specifies its start cue, objective, success cue, failure cue and retry prompt. Confirm completion against fresh frames and the expected mission transition. A loading screen alone gives insufficient evidence. Confirm the in-game retry prompt before selecting it. Increment and persist the attempt count first. Exhausted retry, elapsed-time or action budgets stop the session. Continue to the next mission only when its start cue matches.

Only the proposed gameplay adapter is exposed to the planner. The operator handles pairing and system screens. Keep account tokens, pairing material and unredacted captures on the host.
