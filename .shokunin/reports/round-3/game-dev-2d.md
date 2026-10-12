# game-dev-2d — round 3 (probation)

Claim: add headless UI signal-to-Label update and disconnected-signal control while retaining 17 prior cases. One axis-move: **coverage**. Work commits `a0d3f239a5e989f69e39028d034cc7d4e9a9d3c2`, `d404330f5bfd0f0db0a739eb4e654785a1b0c069`; named non-author verifier `r3-ui-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Wave 1 independent scout/critic and executor reports: `.shokunin/game-dev-2d/reports/r3-ui-scout.md`, `r3-ui-critic.md`, `r3-ui-executor.md`. Wave 2 verifier report: `r3-ui-verifier.md` and committed raw `corpus/lessons/r3-ui-verifier.json`. All four leaves settled, no child delegation observed.
- New `corpus/fixtures/ui_signal_hud.gd` creates CanvasLayer/Label, waits one frame, checks in-tree initial `Score: 0`, emits score 7, asserts in-tree `Score: 7`. Same script under `--disconnect-signal` omits only the connect and fails the same post-emission text assertion. Runner adds two cases without changing the 17 prior case definitions (`a0d3f239a5e989f69e39028d034cc7d4e9a9d3c2`).
- Verifier independently reran `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing`: exit 0, 19/19 PASS, previous 17 PASS, positive output clean, negative exit 2 at intended assertion. Verifier SHA-256 checks all 31 preexisting tracked fixtures unchanged, and scratch-only wrong-callback text mutation also fails the assertion (`r3-ui-verifier.md`).

## Landed changes
- Round 3 claim/closure, fixture, runner, knowledge, raw replay in `a0d3f239a5e989f69e39028d034cc7d4e9a9d3c2`; scorecard binding in `d404330f5bfd0f0db0a739eb4e654785a1b0c069`. Both commits use `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. This report and four scoped leaf reports land last.

## Before → after measurements and per-axis verdicts
- **Coverage improved**: UI cases 0 in `run_battery.py` at `8c8672777795201db747a7cd64dc1f34c97cffe5` → 2 at `d404330f5bfd0f0db0a739eb4e654785a1b0c069`. `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → 19/19 independent PASS in `corpus/lessons/r3-ui-verifier.json`, versus 17/17 in `corpus/lessons/r2-camera-verifier.json`. Disconnected and wrong-callback controls fail the same text assertion.
- **Depth unchanged**: one bounded decision table in `corpus/lessons/r3-ui-headless.md`; no broader decision depth established.
- **Calibration unchanged**: this is a synthetic synchronous signal-to-Label.text property test, not the game's production HUD, real model source, layout, visibility, pixels, or rendering. Runner signatures remain potentially spoofable if a fixture is altered to print success without asserting.

Admitted: one improved axis, none harmed. No promotion claimed; neither a game-source edit nor asset-rights or narrative-canon claim.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — `corpus/lessons/r1-headless-verification.md`, `r2-camera-headless.md`, `r3-ui-headless.md`; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named non-author verifier and committed `corpus/lessons/r3-ui-verifier.json`; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson commands; promotion box remains unchecked.
- [~] No cross-domain bleed and accurate province — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
