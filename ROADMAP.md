# Roadmap

| Stage | Deliverable | Evidence required to advance |
| --- | --- | --- |
| 1. Transport | Pair a stock PS5 and measure observation and input | Reversible menu action, analog movement and release, 20 latency samples, client-specific results |
| 2. Supervisor | Replay labelled observations without hardware | Completion, failure, duplicate acknowledgement, stale video and process restart all yield the expected state |
| 3. First story mission | Start at a named checkpoint and reach a visible completion condition | Trace every attempt and takeover. Reproduce from the same checkpoint on a second setup. |
| 4. Recovery | Recognize failure and use the in-game checkpoint retry | Show a successful recovery and a separate run stopping at the retry limit |
| 5. Continuous gameplay | Advance through two consecutive story objectives | Record elapsed time, intervention count and why the session stopped |

All five stages are proposed. Stage 2 can start with synthetic fixtures while the hardware trial is pending. Track assignments and evidence in [TRACKER.md](TRACKER.md).
