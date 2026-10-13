# game-dev-2d — round 26 — calibration

## Work performed
- Declared one measured slow-clean timeout-margin move in `.shokunin/game-dev-2d/LOG.md` before dispatch. Eight leaf lanes settled before named non-author verifier. Work commit `523ca3eda121b3b214b749b58d02624223d8f100`.
- Changed `corpus/fixtures/timeout_probe.gd` and opt-in `--probe-timeout` path in `run_battery.py` to record three arms: old 0.75s timeout, new 3.0s timeout with same 1.5s postmarker clean delay, and hold-open negative at new bound. Early draft delayed *before* marker; scribe/parent caught mismatch and executor corrected it before author/independent replay. Scratch reviewer old-bound no-marker result is only feasibility, not admission evidence (`reports/r26-timeout-scribe.md`, `reports/r26-timeout-executor.md`).
- Named independent `r26-timeout-verifier` ran `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit 0, **50/50 PASS**, raw `.shokunin/game-dev-2d/corpus/lessons/r26-timeout-verifier.json`, detailed `r26-timeout-detail.json`, report `reports/r26-timeout-verifier.md`. Separate fault meta PASS (`r26-fault-verifier.json`) with intentionally failing inner hang/unrelated cases retained.

## Landed changes
- LOG, SCORECARD, timeout fixture/opt-in runner, cited lesson, eight wave-1 reports, named verifier report, raw three-arm/full/fault JSON: `523ca3eda121b3b214b749b58d02624223d8f100`. This report lands last in its own commit.

## Before → after measurements
- Immutable baseline HEAD `1e4e9c27fd75a5fcf38200a45891fb9c3064bf8e`: 39 ordinary CASES (baseline scout's 40 text-count corrected by AST), full r25 final 50/50; `--probe-timeout` had 0.75s bound and a prior critic-measured 0.394s normal startup (~0.356s margin). At `523ca3eda121b3b214b749b58d02624223d8f100`, named verifier 50/50 with all 50 names/status/exits/signatures unchanged. Tracked same-script detail: old .75s `--delay-clean` marker observed but timeout/actual_exit null/classifier false/reaped; new 3s same 1.5s postmarker delay exits 0 at 1.972s/classifier true; hold-open at 3s marker observed/timeout/classifier false/reaped. Tracked hashes stable across verifier.
- Verdicts: **calibration improved** for this real Godot 4.7.2 deliberately slow clean fixture while preserving this hold-open detection; **coverage unchanged** (39 ordinary), **depth unchanged**, no harmed axis in finite replay. Not arbitrary freeze detection, process-tree cleanup, cross-platform or production startup reliability.
- Constants changed: opt-in timeout 0.75s → 3.0s, fixture postmarker delay 1.5s; cleanup 3s unchanged. No engine/editor source or seeded control mutation, publication, push, merge.

## SHONEN
- [~] Decision/error table with cited raw — `corpus/lessons/r26-timeout-margin.md`; verifier did not review probation box.
- [~] End-to-end task and named non-author raw replay — `reports/r26-timeout-verifier.md`, `corpus/lessons/r26-timeout-verifier.json`; not a promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
