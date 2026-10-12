# game-dev-2d — round 13 (probation)

Claim: a headless SceneTree Tween drives an actual `CanvasItem.modulate` excursion and returns to baseline within bounded process frames; the same assertion rejects skipping Tween start. One axis-move: **coverage**. Work/raw evidence committed `52d0f9e`; named non-author verifier `r13-juice-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Before: Round 12 had 29 ordinary feature/mutant cases and 35/35 with opt-in probes. Round 5 covered `AnimationPlayer` moving `position.x` via direct `advance(0.5)`, not SceneTree Tween scheduling, CanvasItem modulation, or transient return. Round 13 added `tween_flash.gd` and `tween_flash`/`tween_no_start` to ordinary battery. A `Node2D` starts at modulate `(0.7,0.8,0.9,1)`, Tween targets `(1,0.2,0.1,1)` for 0.2 s then baseline for 0.2 s; the fixture samples real `target.modulate` after each frame, for at most 90 frames. No-tween skips only Tween creation and shares the assertion. The case-owned expected ERROR allowance is a narrow comma-terminated prefix; script/parse failures remain disallowed.
- Scout/executor/critic wave, then named non-author verifier. Initial author cap 36 frames failed positive before its return; increasing to 90 yielded return at frame 62. Critic caught initial mismatch between detailed negative `push_error` and an exact bare allowed error; executor corrected the narrow prefix and replayed 31/31. Both adverse steps remain in leaf reports. No leaf delegation, seeded fixture mutation, engine/editor source edits, publishing, or push.
- Independent verifier replayed `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error`: exit 0, **37/37 PASS** (`corpus/lessons/r13-battery-verifier.json`). Positive exit 0: observed nonbaseline `(0.7041,0.7918,0.8891,1)` then original baseline at frame 62. No-start exit 2 on exact assertion after 90 frames, transient/restored both false, final baseline; no warning or setup/parse/other error. `--fault-injection` meta PASS (`corpus/lessons/r13-fault-regression.json`). A scratch-only disabled-Tween mutation made the positive fail while negative and other ordinary cases passed. Verifier runner/new fixture hashes unchanged. See `corpus/lessons/r13-headless-tween-flash.md` and `reports/r13-juice-verifier.md`.

## Before → after and per-axis verdicts
- **Coverage improved**: 29 → **31** ordinary feature/mutant cases, independently showing a distinct Tween-to-modulate transient-and-return and no-start control; all previous 29 retained.
- **Calibration unchanged**: only an exact case-owned negative error prefix was added under existing classifier behavior.
- **Depth unchanged**: bounded lesson documents evidence and limits; no second axis move asserted.

Admitted: one improved axis, no observed harmed axis. This proves headless property state, **not** rendered brightness, perceived flash, visual quality, universal timing, or production game integration.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r13; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named non-author replay and scratch counterfactual, raw evidence committed; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
