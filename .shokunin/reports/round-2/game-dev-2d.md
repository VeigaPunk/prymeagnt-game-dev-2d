# game-dev-2d — round 2 (probation)

Claim: add camera-follow headless positive and no-follow control to the scratch-copy Godot battery while keeping existing 15 cases passing. One axis-move: **coverage**. Work commits: `7f3c927`, `aece3036bccd73f67b9b4aaf5ab3c690f8cab70d`. Named non-author verifier: `r2-camera-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Wave 1 scout/executor/critic reports: `.shokunin/game-dev-2d/reports/r2-camera-scout.md`, `r2-camera-executor.md`, `r2-camera-critic.md`. The executor's initial result is superseded by an integrated same-script effective-center test after critic feedback. Wave 2 independent replay: `r2-camera-verifier.md` and committed raw `.shokunin/game-dev-2d/corpus/lessons/r2-camera-verifier.json` (17/17 PASS).
- Added `corpus/fixtures/camera_follow.gd`: parented Camera2D follows a target moved to `(120,-53)` and `get_screen_center_position()` changes >100 units and matches the target within `0.01`; same script with `--no-follow` detaches the camera and exits 2 on the tracking assertion. Added two runner case definitions; existing 14 plus opt-in scene mutant remain.
- Named verifier independently reran `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` (exit 0, 17/17), confirmed clean positive output and only the intended no-follow error; hash-checked all 30 prior tracked fixture paths unchanged before and after. See `.shokunin/game-dev-2d/reports/r2-camera-verifier.md`.

## Landed changes
- Round 2 claim, wave dispatch, closure, camera fixture, runner cases, evidence and bounded lesson in work commit `7f3c927`; scorecard evidence bound to the work hash in `aece3036bccd73f67b9b4aaf5ab3c690f8cab70d`. Both commits use `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. Reports are committed last after this work.

## Before → after measurements and per-axis verdicts
- **Coverage improved**: camera cases 0 at `60a41b4e1b2c980e4725fc74ed2f5663a96d6e21` → 2 at `aece3036bccd73f67b9b4aaf5ab3c690f8cab70d`, counted from `CASES` in `.shokunin/game-dev-2d/corpus/fixtures/run_battery.py`; `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → 17/17 PASS in committed independent `corpus/lessons/r2-camera-verifier.json`, versus round-1 15/15. The two cases share one behavioral assertion; a detached camera fails it with exit 2. No previously tracked fixtures changed.
- **Depth unchanged**: bounded decision/error table added in `.shokunin/game-dev-2d/corpus/lessons/r2-camera-headless.md`, but no independent depth improvement claimed.
- **Calibration unchanged**: verifier removed `make_current()` in scratch and still obtained PASS; `is_current()` and effective center do **not** establish rendered viewport selection. This proves only headless Camera2D screen-center behavior, not pixels, visual framing, smoothing, zoom, export, or product readiness. Existing runner also checks signatures/exit codes rather than rejecting every unrelated `ERROR:`; final positive output is clean.

Admitted: coverage improved and no owned axis harmed. No promotion claimed. The previous executor's direct hierarchy observation was insufficient; the integrated test and non-author replay are the accepted evidence.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — `.shokunin/game-dev-2d/corpus/lessons/r1-headless-verification.md` and `r2-camera-headless.md`; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — independent verifier `r2-camera-verifier`, committed raw `r2-camera-verifier.json`; promotion box remains unchecked.
- [~] Instructions executable without oral context — `.shokunin/game-dev-2d/corpus/README.md` and `r2-camera-headless.md`; no promotion review.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`, fixture hash verification; no promotion review.
