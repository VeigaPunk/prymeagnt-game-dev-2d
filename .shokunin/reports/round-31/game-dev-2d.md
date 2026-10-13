# game-dev-2d — round 31 — calibration

## Work performed
- Declared continued Button focus after first completed action as the single calibration claim in LOG before dispatch. Eight wave-1 leaves and named non-author verifier settled. Work commit `198432ee7aac49b6f4c565c31165fed3b0269f4d`.
- Added `--lose-focus-after-first` to the Button fixture and one ordinary runner case. Same first focused press/release reaches receipt1/Activated 1; the treatment calls `release_focus()` after release1, verifies null GUI owner and Button.has_focus false before second input and after both second edges, which remain receipt1/Activated 1. Continuously focused positive still reaches receipt2/Activated 2; disconnected and initially-unfocused negatives still fail intended release1. Input edges and signal wiring are unchanged.
- Named non-author `r31-focus-loss-verifier` full default-path `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit0 **54/54 PASS** (43 ordinary +2 mutants +9 opt-in), all prior r30 53 verdict/actual_exit/signature tuples unchanged. Direct focused vs treatment repeated; new row exit0 PASS. Disposable sabotage removes only focus release, retaining focus assertion, exit2 intended mid-sequence assertion. Raw byte-identical `corpus/lessons/r31-focus-loss-verifier.json`, report `reports/r31-focus-loss-verifier.md`; separate fault-injection outer PASS with intentional inner adverse FAIL raw `r31-fault-verifier.json`. Source hashes stable during verifier replay.

## Landed changes and before → after
- LOG/SCORECARD, Button fixture and runner, lesson, wave and verifier reports/raw: `198432ee7aac49b6f4c565c31165fed3b0269f4d`. This report lands separately after work commit.
- Before immutable r30 HEAD `be1f5e4bf7827a3b978ad88c0fdb2bd9f4a2b75d`: 42 ordinary/53 full, first-action no-focus control only; second activation requires focus in positive but no mid-sequence focus-loss control. After: 43 ordinary/54 full, confirmed second action remains receipt1 when focus is explicitly removed after first action. **Calibration improved** in bounded headless synthetic `root.push_input(ui_accept)` route; **depth unchanged**, **coverage unchanged as axis** (extra row is this calibration control), none harmed in finite replay. No pointer/rendered UI, physical timing/debounce, accessibility, general production behavior or arbitrary mutation-proof claim.
- Constants changed: 42→43 ordinary, 53→54 full, new treatment expected exit0/receipt1/Activated 1 after action two. No engine/editor or seeded control mutation, publishing, push, merge.

## SHONEN
- [~] Decision/error table with cited source — `corpus/lessons/r31-button-focus-loss.md`; not independent promotion check.
- [~] End-to-end task and named non-author replay — `reports/r31-focus-loss-verifier.md`, `corpus/lessons/r31-focus-loss-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
