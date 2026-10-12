# game-dev-2d — round 11 (probation)

Claim: shared production process/classifier accepts an exact expected diagnostic emitted by a real Godot process, then rejects the same script/exit/signature when Godot emits a second unrelated `push_error`. One axis-move: **calibration**. Work commits `8728fe7667b4853b286022cc7411a4323dae662c`, `77baab5de1a84729dcb6c4d7a41912e6d223efa8`. Named non-author verifier `r11-godot-error-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Before: r7 injected Python subprocess text, r9 edited real captured Godot strings; no paired actual Godot-emitted unrelated ERROR check. Wave 1 scout/executor/critic, wave 2 verifier; reports `.shokunin/game-dev-2d/reports/r11-godot-error-*.md`. Scout suggested reusing an existing negative fixture in scratch; executor instead added a minimal new GDScript and aligned exit to 1, with a case-owned exact expected error. Critic independently replayed and bounded the claim. No leaf delegation.
- New `corpus/fixtures/godot_error_probe.gd` is copied to scratch. `--probe-godot-error` runs two real `godot --headless --path <scratch> --script res://godot_error_probe.gd` commands, the second with `--unrelated-error`, both 8s bounded. Both exit 1 and emit exact expected `ERROR: EXPECTED_NEGATIVE: deliberate assertion rejected` once with Godot backtrace; fault additionally emits exact `ERROR: UNRELATED_FAULT: unrelated engine diagnostic` once with its backtrace. Same `classify_process` used by ordinary cases returns true then false. Meta requires exact diagnostics/exit/signature/script and expected inner verdicts; no captured-output string editing.
- Independent combined command `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error` → exit 0, **33/33 PASS** in committed `corpus/lessons/r11-battery-verifier.json`; paired raw commands/output/classifications in `corpus/lessons/r11-godot-error-verifier.json`. `--fault-injection` meta PASS in `corpus/lessons/r11-fault-regression.json`; export launch regression raw in `corpus/lessons/r11-launch-regression.json`. Verifier's disposable `/tmp` sabotage disabling unrelated-error filtering or suppressing extra push_error each made meta FAIL and overall exit 1. Runner and new fixture hashes unchanged by verifier.

## Landed changes
- Declaration/closure, runner/new fixture, independent raw JSON and bounded lesson in `8728fe7667b4853b286022cc7411a4323dae662c`; scorecard evidence hash in `77baab5de1a84729dcb6c4d7a41912e6d223efa8`. Both commits use `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. Leaf reports and this report land last.

## Before → after measurements and per-axis verdicts
- **Calibration improved**: at r10 `b4dee9a`, no actual paired Godot process ERROR emission; at `77baab5de1a84729dcb6c4d7a41912e6d223efa8`, same script/exit/signature has real expected-only diagnostic classified true and expected+unrelated diagnostic classified false, independent 33/33 and sabotage FAIL. This is one push_error path on installed Godot, not all diagnostic formats or real crash behavior; stdout/stderr attribution not established because streams are combined.
- **Coverage unchanged**: prior 27 original/mutant cases and opt-in export startup retained; one new meta record calibrates verdict, not game feature coverage.
- **Depth unchanged**: `corpus/lessons/r11-real-godot-diagnostics.md` bounds decisions; no separate depth move.

Admitted: calibration improved, no harmed axis. No production game, visual, rights or publishing claims.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r11; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named verifier `r11-godot-error-verifier`, committed raw paired/battery JSON; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
