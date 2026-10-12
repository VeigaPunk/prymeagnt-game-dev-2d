# game-dev-2d — round 15 (probation)

Claim: headless Godot `TextureProgressBar` receives a health-like signal, changes value from 100 to 35 and emits exactly one `value_changed(35)` receipt; a same-fixture disconnected health signal fails the same assertion. One axis-move: **coverage**. Work/raw evidence committed `d3b9ae6`; named non-author verifier `r15-gauge-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Before: Round 14 had 31 ordinary feature/mutant cases and 38/38 combined. Round 3 UI covered signal-driven `Label.text`, not a Range Control value or its change receipt. The fixture builds an in-tree CanvasLayer/TextureProgressBar, sets min/max 0/100 and initial value 100, connects `value_changed` after setup, then emits `health_changed(35)`. It asserts value 35, one callback carrying 35 and valid setup. `--disconnect-signal` skips only health handler connection; identical assertion sees actual value 100, count 0 and receipt sentinel -1, exits 2 on the case-owned exact expected ERROR.
- Scout/executor/critic wave then named non-author verifier. Critic's initial scratch replay found disconnected case incorrectly classified FAIL because its expected error had not been allowed; executor added only the exact case-owned allowance, reran author 33/33. That adverse history remains in `reports/r15-gauge-critic.md` and executor report. Scout separately tested clamp semantics in scratch; the admitted fixture has only an in-range 35 assignment, so **no clamp claim**. No leaf delegation, seeded fixture mutation, engine/editor source edits, publishing or push.
- Independent verifier command `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-audio-warning` → exit 0, **40/40 PASS** (33 ordinary + seven opt-in), `corpus/lessons/r15-gauge-verifier.json`. Gauge outputs have no warnings/setup/parse/extra errors. `--fault-injection` meta PASS (`corpus/lessons/r15-fault-regression.json`). Scratch-only removal of the health connection made positive default battery fail. Verifier hashed 40 tracked fixture paths unchanged. See `corpus/lessons/r15-health-gauge.md`, `reports/r15-gauge-verifier.md`.

## Before → after and per-axis verdicts
- **Coverage improved**: 31 → **33** ordinary cases, distinct TextureProgressBar value/receipt plus disconnected control; prior cases retained.
- **Calibration unchanged**: exact negative assertion accepted by existing classifier; no general classifier change.
- **Depth unchanged**: bounded lesson/replay do not assert a second axis move.

Admitted narrowly: one improved axis, no observed harmed axis. Headless Control state and callback are **not** range-clamping evidence, rendered fill pixels, UX quality, or production health integration.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r15; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named verifier replay and scratch counterfactual, raw evidence committed; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
