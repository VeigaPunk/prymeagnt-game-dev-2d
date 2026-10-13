# game-dev-2d — round 24 — coverage

## Work performed
- Declared bottom-edge Camera2D active-center clamp and far-bottom control before dispatch in `.shokunin/game-dev-2d/LOG.md`. Eight wave-1 leaves and named non-author `r24-bottom-verifier` settled sequentially. Work commit `b32fc5af878eea457e0c9adc011511fd0afd1f22`.
- Extended only `corpus/fixtures/camera_limit.gd` and `run_battery.py`: authored bottom assertion 1000 in both arms, far control changes camera.limit_bottom to 100000. Duplicate pair in first draft removed before final 39-case author replay. Executor author replay was **38/39**, failing only export readiness with `ERROR: Prepare Template: The given export path doesn't exist.`; raw adverse `.shokunin/game-dev-2d/corpus/lessons/r24-export-adverse.json`. This failure is not reclassified as a pass.
- Named independent verifier ran `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit 0, **50/50 PASS** (39 ordinary +2 mutants +9 opt-in), raw `corpus/lessons/r24-bottom-verifier.json` and `reports/r24-bottom-verifier.md`. Scratch authored-bottom sabotage exited 2 on intended bottom assertion. Separate fault meta top-level PASS (`corpus/lessons/r24-fault-verifier.json`) with intentional inner FAILs preserved.

## Landed changes
- LOG, SCORECARD, fixture/runner, cited lesson, all eight leaf reports, verifier report, full/fault raw JSON **and adverse export JSON**: `b32fc5af878eea457e0c9adc011511fd0afd1f22`. This report lands separately after the work commit.

## Before → after measurements
- Immutable pre-change `3b23caa25f00d3929a863ba9d3515be9aa5bb760` has 37 declared ordinary CASES, r23 full replay 48/48 PASS, no bottom pair (`reports/r24-baseline-scout.md`; scout's text count 38 was corrected by AST). At `b32fc5af878eea457e0c9adc011511fd0afd1f22`, named verifier full command above: 50/50, all prior 48 status/signature/exit results unchanged. Positive bottom y=968 from 1000 minus active viewport half-height 32, target 2000. Far-bottom camera limit 100000 follows target and fails same authored assertion exit 2, no setup error; scratch sabotage matches.
- Verdicts: **coverage improved** for bounded headless bottom-edge Camera2D center and causal control; **depth unchanged**, **calibration unchanged**, none harmed in finite default-path replay. The author relative-`--runs` export FAIL remains unresolved adverse evidence. One later passing export of 73,703,800 bytes does not prove export reliability or close r16/r20/r24 discrepancies. No rendered framing or production camera claim.
- Constants: bottom 1000, far bottom 100000, target y=2000, dynamic viewport half-height (battery observed 32), epsilon 0.01. No engine/editor source or seeded control mutation, publication, push, merge.

## SHONEN
- [~] Real decision/error table with cited source — `corpus/lessons/r24-camera-bottom.md`; round verifier did not review probation box.
- [~] End-to-end task and named non-author replay — `reports/r24-bottom-verifier.md`, raw `corpus/lessons/r24-bottom-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
