# game-dev-2d — round 23 — coverage

## Work performed
- Declared left-edge Camera2D center clamp and far-left control before dispatch, with viewport-width correction recorded in `.shokunin/game-dev-2d/LOG.md`. Eight wave-1 leaves then named non-author verifier settled. Work commit `a92c5c243d75f766c394fda6d401bc29ad48dc0e`.
- Extended only `corpus/fixtures/camera_limit.gd` and `run_battery.py`: same authored assertion bound -1000 in both arms; only the camera's left limit changes to -100000 for control. Executor initially duplicated the assignment and varied the assertion boundary; corrected before author/independent replays (`reports/r23-left-executor.md`, LOG).
- Named `r23-left-verifier` independently executed `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit 0, **48/48 PASS** (37 ordinary +2 mutants +9 opt-in), raw `corpus/lessons/r23-left-verifier.json` and `reports/r23-left-verifier.md`. Scratch authored-left sabotage failed intended assertion. Separate fault meta PASS, raw `corpus/lessons/r23-fault-verifier.json`; intentionally failing inner hang/unrelated cases remain FAIL.

## Landed changes
- LOG, SCORECARD, camera fixture/runner, cited lesson, eight wave-1 leaf reports, verifier report and raw JSON: `a92c5c243d75f766c394fda6d401bc29ad48dc0e`. This report lands separately after that commit.

## Before → after measurements
- Pre-change HEAD `0d73a4c09300f201ba0233b73e4f3548c15201bb`: 35 ordinary CASES and 46/46 prior full results PASS (`reports/r23-baseline-scout.md`). At `a92c5c243d75f766c394fda6d401bc29ad48dc0e`, named verifier command above 48/48 with prior 46 unchanged. Left positive center x=-968 from authored -1000 + battery viewport half-width 32, target -2000; far-left camera limit -100000 followed target x=-2000 and failed the same intended left assertion, exit 2, not setup. A separate scout scratch viewport width 720 gave x=-640 under the same dynamic formula; no hard-coded viewport expectation.
- Verdicts: **coverage improved** for headless left-edge Camera2D center with causal control; **depth unchanged**, **calibration unchanged**. None harmed in finite replay. No rendered framing, production camera, remaining edges, or export-reliability inference. Prior r16 export intermittence and r20 relative-`--runs` exception remain unresolved.
- Constants: authored left -1000, far left -100000, target x=-2000, dynamic viewport half-width (battery observed 32), epsilon 0.01. No engine/editor source or seeded control mutation, publication, push, merge.

## SHONEN
- [~] Real decision/error table with cited source — `corpus/lessons/r23-camera-left.md`; verifier checked round, not probation box.
- [~] End-to-end task and named non-author replay — `reports/r23-left-verifier.md`, raw `corpus/lessons/r23-left-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
