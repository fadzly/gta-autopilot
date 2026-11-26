# Validation guide

| Evidence level | Meaning |
| --- | --- |
| Proposed | Design or acceptance criteria exist. |
| Upstream reported | The upstream source describes or demonstrates the behavior. |
| Tested | A contributor ran the exact case and attached a reproducible report with the outcome, including failures. |
| Validated | A second contributor reproduced the stated pass condition on an independently described setup and linked both reports. |

## First hardware run

1. Record project and bridge revisions, host OS, PS5 firmware, game build, client version and checkpoint. Start with a manually opened, reversible in-game menu.
2. Capture the baseline, move the highlight once and capture the new frame. Return to the baseline. Repeat 20 times. Record input dispatch and first visible change on the same monotonic clock. Report median, p95, missing changes and timeouts.
3. In a stable scene, give a short stick input and release. Check for motion after release. Test operator stop during a short sequence and observe the final controller state.
4. Repeat the client handshake and observation/action trial for each claimed client. Record any untested OS or client explicitly.

## Mission run

Write down the visible success and failure cues before starting. Set attempt and time limits. Log every attempt, checkpoint restart and human input. Attach a redacted trace or short clip showing both the initial state and completion cue. A human-assisted completion is recorded separately. Report success as completed attempts divided by all attempts and give the actual counts.

Use a run-report issue for each setup. Link independent reproduction from the tracker. Remove handles, notifications, pairing data and tokens before publishing.
