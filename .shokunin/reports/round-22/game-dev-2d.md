# game-dev-2d — round 22 — calibration

## Work performed
- Declared one paired real-Godot normal exit versus marker-before-timeout contrast in `.shokunin/game-dev-2d/LOG.md` before dispatch. Eight wave-1 leaves and named non-author `r22-timeout-verifier` settled sequentially. Work commit `2758ec058b7cc863c8cef0bd004a8d421ad5fe52`.
- Added `timeout_probe.gd` and opt-in `--probe-timeout` under `.shokunin/game-dev-2d/corpus/fixtures/`; ordinary CASES unchanged. Parent caught executor's initial confusion of cleanup return with actual timeout exit; corrected record distinguishes `actual_exit=null` and cleanup -9 before independent replay (`reports/r22-timeout-executor.md`, LOG).
- Named verifier full default-path command `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit 0, **46/46 PASS** (35 ordinary +2 mutants +9 opt-in). Raw `corpus/lessons/r22-timeout-verifier.json` and `r22-timeout-detail.json`; separate `--fault-injection` top-level meta PASS at `r22-fault-verifier.json`, whose expected inner hang and unrelated-error cases remain FAIL. Verifier report `.shokunin/game-dev-2d/reports/r22-timeout-verifier.md`.

## Landed changes
- LOG, SCORECARD, fixture/runner, decision-table lesson, eight leaf reports, verifier report and three raw JSON artifacts: `2758ec058b7cc863c8cef0bd004a8d421ad5fe52`. This report is committed separately after that work commit.

## Before → after measurements
- At pre-change `8f87c585bfcf6a7eb56b8b84cb4f95420aa66f90`, 35 ordinary and 45/45 prior full-battery records PASS; no paired real timeout probe (`reports/r22-baseline-scout.md`). At `2758ec058b7cc863c8cef0bd004a8d421ad5fe52`, named verifier command above 46/46, prior 45 unchanged. Same `res://timeout_probe.gd` and marker in both arms: normal rc0 true; hold-open marker captured while live, `actual_exit=null`, `TIMEOUT after 0.75 seconds`, classifier false; cleanup exit -9 and direct child not live after 3s bound.
- Verdicts: **calibration improved** for this specific real-Godot direct-child timeout contrast; **coverage unchanged** (ordinary 35), **depth unchanged**. None harmed in finite replay. Critic found only ~0.356s positive-startup margin at observed host load; potential false negatives remain. Detached grandchild surviving timeout in reviewer scratch excludes process-tree cleanup. No general freeze, other-platform or export reliability claim; R16 intermittent export and r20 relative-path exception remain unresolved.
- Constants: timeout 0.75s, cleanup bound 3s, fixture hold 30s, marker `TIMEOUT_PROBE: expected signature`, normal exit 0, cleanup -9 observed. No engine/editor source or seeded control edit, publication, push, merge.

## SHONEN
- [~] Real decision/error tables with cited sources — `corpus/lessons/r22-real-timeout.md`, verifier checked this round not probation box.
- [~] End-to-end task and named non-author replay — `reports/r22-timeout-verifier.md`, raw `corpus/lessons/r22-timeout-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
