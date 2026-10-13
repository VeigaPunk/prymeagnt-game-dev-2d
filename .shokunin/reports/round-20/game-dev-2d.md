# game-dev-2d — round 20 — coverage

## Work performed
- Corrected the stale standing-brief baseline before dispatch: the branch tip was already round 19, not round 1. Claim and eight-leaf wave specification are in `.shokunin/game-dev-2d/LOG.md` (round 20).
- Extended `corpus/fixtures/camera_limit.gd` and `run_battery.py` with a top-limit positive and far-top-bound control; change landed in work commit `bf8bc9634b08bdb2ae64a9434b837735b748fe00`. Executor/critic/mutation reports are `.shokunin/game-dev-2d/reports/r20-*.md`.
- Named non-author `r20-top-verifier` replayed the default-path full battery, exit 0, 44/44 PASS; committed raw artifact `.shokunin/game-dev-2d/corpus/lessons/r20-top-verifier.json`, with interpretation in `.shokunin/game-dev-2d/reports/r20-top-verifier.md`. Top center y=-968 at limit -1000, target y=-2000; far-top center y=-2000 failed intended assertion, and disposable scratch sabotage likewise failed. Prior right cases retained PASS.
- The first parent pre-change run with an explicit relative `--runs` hit `StopIteration` at `run_battery.py:245` during the export diagnostic probe; the default-path pre-change 42/42 and after 44/44 passed. This adverse relative-path event remains unresolved, not a top regression or export-reliability pass (`LOG.md`, round 20).

## Landed changes
- Round-20 LOG declaration/correction/outcome, SCORECARD measurement, top-limit fixture/runner, cited lesson, eight wave-1 leaf reports, verifier leaf report and raw JSON: `bf8bc9634b08bdb2ae64a9434b837735b748fe00`. The report is committed separately **after** this work commit.

## Before → after measurements
- `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution`: pre-change HEAD `3d19377a604df726377e53b8007b284a3607875d` yielded 42/42 = 33 ordinary + 2 mutants + 7 opt-in with the default path (pre-change raw `corpus/live/runs/20261013T005255742688Z/verdicts.json`); named verifier at `bf8bc9634b08bdb2ae64a9434b837735b748fe00` yielded 44/44 = 35 ordinary + 2 mutants + 7 opt-in, raw committed `corpus/lessons/r20-top-verifier.json`. An independently extracted HEAD baseline also found 33 CASES (`reports/r20-baseline-scout.md`).
- Verdicts: **coverage improved** (headless top-edge center-clamp and causal far-top control); **depth unchanged** (existing Camera2D mechanic); **calibration unchanged** (only exact expected diagnostic allowlist extended). None harmed in the finite independent replay. Admitted on these bounds only: no rendered pixels, production camera, other edges, or export reliability.
- Constants changed: top -1000, far top -100000, target y=-2000, epsilon 0.01; viewport half-height computed dynamically (observed 32). No engine/editor source or seeded control changes, publication, push, or merge.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — `corpus/lessons/r20-top-camera.md`; verifier checked the round, not this probation box.
- [~] End-to-end domain task executed and logged; named non-author `r20-top-verifier` replay `reports/r20-top-verifier.md` and raw `corpus/lessons/r20-top-verifier.json`; not a promotion check.
- [ ] Instructions executable without oral context — not separately checked by non-author.
- [ ] No cross-domain bleed; PROVINCE accurate — not separately checked by non-author.
