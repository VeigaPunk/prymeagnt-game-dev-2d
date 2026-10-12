# game-dev-2d — round 8 (probation)

Claim: finite headless CharacterBody2D motion contacts/blocks on the authored TileMapLayer cell `(2,3)` and the identical sweep passes through that occupied cell after scratch-only polygon removal. One axis-move: **coverage**. Work commits `2fd8eeae2226092ada5c3d1e613063bca0dd8fe4`, `aeefb076a428971e3fcca5ddb2406be1685d5046`. Named non-author verifier `r8-contact-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Before: r4 `level_probe.gd` checked polygon metadata only; r7 25/25. Wave 1 scout/executor/critic, wave 2 named non-author verifier; scoped reports `.shokunin/game-dev-2d/reports/r8-contact-*.md`. Critic caught early Ground-only attribution; executor added contact-point mapping to `(2,3)`. Verifier scratched in another collidable tile `(2,2)` and observed fail-closed attribution; no leaf delegation.
- New `corpus/fixtures/contact_probe.gd`: instantiate original authored level in scratch, await bounded physics frames, sweep 6×6 CharacterBody2D downward 40px from `(40,36)`, verify polygon and occupied cell, Ground contact mapped to `(2,3)` and blocked end `(40,44.82812)`; paired scratch duplicate TileSet removes atlas polygon, validates polygon count 0 and collision=null with end `(40,76)` crossing tile, then raises expected exit-2 assertion. Wrong setup exits 3, not the expected negative. `run_battery.py` adds `contact_runtime` and `contact_no_collision`.
- Independent `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → exit 0, **27/27 PASS** (25 retained plus two), raw committed `corpus/lessons/r8-contact-verifier.json`; contact positive exit 0, negative exit 2/expected assertion, no unrelated parse/setup ERROR; all 36 tracked fixture files hash-identical before/after verifier replay. Direct copied-project no-collision returned exit 2. Test is Godot 4.7.2 Linux headless; no rendered level or production project claim.

## Landed changes
- Declaration/closure, fixture/runner, independent raw JSON, bounded decision table in `2fd8eeae2226092ada5c3d1e613063bca0dd8fe4`; scorecard evidence hash in `aeefb076a428971e3fcca5ddb2406be1685d5046`. Both commits use `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. Leaf reports and this report land last.

## Before → after measurements and per-axis verdicts
- **Coverage improved**: from 0 runtime body-vs-tile cases / 25/25 at r7 (`4055e47`) to two runtime-contact/control cases / independent 27/27 at `aeefb076a428971e3fcca5ddb2406be1685d5046`; raw `corpus/lessons/r8-contact-verifier.json` records mapped contact and pass-through endpoints. This is one authored tile/sweep only, not varied collision normals, rendering, or level playability.
- **Depth unchanged**: `corpus/lessons/r8-runtime-contact.md` records a bounded table; no targeted decision-table move.
- **Calibration unchanged**: prior fault-injection detection remains in r7; no new classifier threshold move.

Admitted: coverage improved, no harmed axis. Verifier described conditional pass because attribution is scoped to current scene geometry and contact-point mapping; this qualification is retained, not generalized.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r8; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named verifier `r8-contact-verifier`, committed 27/27 raw JSON; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md`, lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
