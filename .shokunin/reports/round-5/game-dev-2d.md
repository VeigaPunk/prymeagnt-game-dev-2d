# game-dev-2d — round 5 (probation)

Claim: a headless AnimationPlayer property track changes after bounded advance, while a zero-speed played animation fails the same assertion; retain 21 prior cases. One axis-move: **coverage**. Work commits `cf0cf9708aab214a61c1fcb74a10d5fb89dffb67`, `f8f7286cfdd7bc0e54d7b6ad978be5b3ef7fef52`. Named non-author verifier `r5-anim-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Wave 1 scout/executor/critic evidence `.shokunin/game-dev-2d/reports/r5-anim-scout.md`, `r5-anim-executor.md`, `r5-anim-critic.md`; wave 2 independent replay `r5-anim-verifier.md`. All leaves settled without delegation. Critic first reviewed before implementation and marked evidence pending; verifier reviewed the final fixture. Initial no-play control was changed to played-at-zero-speed before final replay.
- Added `corpus/fixtures/animation_property.gd` with AnimationPlayer TYPE_VALUE track at `.:position:x` from x=0 at t=0 to x=120 at t=1. Starts at x=0, plays, synchronously advances 0.5, asserts x≈60. Same script `--stuck` plays at speed_scale=0, observes x=0 and fails same assertion at exit 2. Runner adds two cases (`cf0cf9708aab214a61c1fcb74a10d5fb89dffb67`).
- Named verifier reran `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing`: exit 0, **23/23 PASS** in committed `corpus/lessons/r5-animation-verifier.json`; old 21 retained. Verifier removed both track keys in disposable scratch; positive then exited 2 at the same assertion. All 34 prior tracked fixture hashes unchanged (`r5-anim-verifier.md`).

## Landed changes
- Round-5 declaration/closure, fixture/runner, raw independent replay, decision boundaries in `cf0cf9708aab214a61c1fcb74a10d5fb89dffb67`; scorecard bound to hash in `f8f7286cfdd7bc0e54d7b6ad978be5b3ef7fef52`. Both commits attributed to `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. This report and four scoped leaf reports land last.

## Before → after measurements and per-axis verdicts
- **Coverage improved**: animation cases 0 at `c6bf3b1` → 2 at `f8f7286cfdd7bc0e54d7b6ad978be5b3ef7fef52`, counted from runner's `CASES`; command `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → independent 23/23 in `corpus/lessons/r5-animation-verifier.json`, compared with 21/21 in `corpus/lessons/r4-level-verifier.json`. Zero-speed and trackless scratch controls both fail the property assertion.
- **Depth unchanged**: bounded decision table `corpus/lessons/r5-animation-headless.md` but no broader decision-rule move.
- **Calibration unchanged**: synthetic in-memory property advancement only, not rendered animation, visual smoothness, game integration, audio, or production juice.

Admitted: one improved axis, no harmed axis. No promotion or publishing.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons r1 through r5; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — verifier `r5-anim-verifier`, committed `corpus/lessons/r5-animation-verifier.json`; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson commands; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
