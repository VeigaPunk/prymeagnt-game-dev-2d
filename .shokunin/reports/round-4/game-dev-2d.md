# game-dev-2d — round 4 (probation)

Claim: load an authored level tile with collision geometry and detect removal of that geometry without disturbing the cell or earlier cases. One axis-move: **coverage**. Work commits `543fe2c43cd77e8edd8aac8037493422e786c9c8`, `045724d33979001b5cff1e4fb1f8c57e0a43c480`; final named non-author verifier `r4-level-verifier-final` (`openai-codex/gpt-6-luna`).

## Work performed
- Wave 1 leaf scout/executor/critic reports `.shokunin/game-dev-2d/reports/r4-level-scout.md`, `r4-level-executor.md`, `r4-level-critic.md`. Wave 2 `r4-level-verifier` initially held its verdict due to unexpected RID/resource-leak diagnostics in the level positive. After the orchestrator added the instantiated level to SceneTree and freed it after a frame, that verifier replayed successfully (`r4-level-verifier.md`); separately dispatched final non-author `r4-level-verifier-final` confirmed clean 21/21 (`r4-level-verifier-final.md`). The HOLD remains in `LOG.md`; no leaf delegation observed.
- New `corpus/fixtures/level_collision/level_scene.tscn` authors TileMapLayer cell `(2,3)` from atlas source 0, with physics-layer-0 four-point polygon. `level_probe.gd` loads/instantiates the scene, inspects occupied cell source/TileData/polygon, and checks it. Same probe `--no-collision` removes the collision polygon from a duplicate TileSet while preserving occupied cell. Runner adds positive and opt-in mutant (`543fe2c43cd77e8edd8aac8037493422e786c9c8`).
- Final independent verifier command `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → exit 0, **21/21 PASS** in committed `corpus/lessons/r4-level-verifier.json`. Level positive output clean of ERROR/WARNING/leaks; mutant exits 2 at exact intended assertion. Prior 19 retained; all 32 prior tracked fixture hashes unchanged (`r4-level-verifier-final.md`). Earlier verifier additionally checked scratch preserved source id 0/cell and falsified polygon and occupancy separately (`r4-level-verifier.md`).

## Landed changes
- Round-4 declaration, closure, fixture, runner, decision table, raw independent result in `543fe2c43cd77e8edd8aac8037493422e786c9c8`; scorecard linked to hash in `045724d33979001b5cff1e4fb1f8c57e0a43c480`. Both commits attributed to `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. This report and five scoped leaf reports land last.

## Before → after measurements and per-axis verdicts
- **Coverage improved**: level cases 0 at `23fe204` → 2 (one positive and one opt-in collision-removed mutant) at `045724d33979001b5cff1e4fb1f8c57e0a43c480`; `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → independent 21/21 PASS (`corpus/lessons/r4-level-verifier.json`) versus prior 19/19 (`corpus/lessons/r3-ui-verifier.json`). Authored polygon missing from occupied tile triggers targeted assertion.
- **Depth unchanged**: `corpus/lessons/r4-level-headless.md` describes a bounded decision table, no independent depth move.
- **Calibration unchanged**: proves *authored TileData collision polygon metadata* at an occupied cell, not runtime physics contact/blocking, rendered level, visual composition or production-level quality. Original 21/21 before cleanup had leak errors and was not used for admission; runner generally does not reject all extraneous ERROR strings, final raw output was inspected.

Admitted: coverage improved, none harmed. No promotion or asset-rights claim.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — `corpus/lessons/r1-headless-verification.md` through `r4-level-headless.md`; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — two named non-author verifiers and committed `corpus/lessons/r4-level-verifier.json`; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson commands; promotion box remains unchecked.
- [~] No cross-domain bleed, province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
