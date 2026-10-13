# game-dev-2d — round 37 — calibration

## Work performed
- Declared same-wiring HSlider focus-absence causal control before eight wave-1 leaves. Work commit `cb05ab13dd11cedf02fb3642a05d8c7db4dcf1d6`. Godot 4.7.2 focused arm: explicit min0 max10 step1 initial5, signal/Label connected, parsed fresh `ui_right` then `ui_left` press/release actions, viewport focus slider before each; value 5→6→5, receipts `[6,5]`, Label `Value 6`→`Value 5`. No-focus arm omits `grab_focus` only, owner not slider before each, same actions leave value5 after both, receipts `[]`, Label `Value 5`, then intended exit2 diagnostic. Existing disconnected-signal arm stays focused and moves 5→6→5 without receipts. Executor's first full run failed because a draft matched observation instead of terminal error and lacked exact negative classifier; failure retained as scratch telemetry and corrected before final replay.
- Named non-author `r37-focus-verifier` default-path full `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit0 **62/62 PASS** (51 ordinary +2 mutants +9 opt-ins). Full r36 named-verifier **61** `(verdict,actual_exit,signature)` rows unchanged, one new expected exit2 PASS. Raw byte-identical `corpus/lessons/r37-focus-verifier.json`, report `reports/r37-focus-verifier.md`; separate fault-injection outer PASS with intentional inner timeout/unrelated-error FAIL (`r37-fault-verifier.json`). Scratch forced-grab sabotage fails no-focus setup before actions, not the expected post-action negative. Tracked hashes stable. Verifier initially reported a misleading subset count of 52 prior rows; report corrected to full 61 after independent parent comparison.

## Landed changes and before → after
- LOG/SCORECARD, `slider_adjust.gd`, runner no-focus row/classifier, lesson, wave and verifier reports/raw: `cb05ab13dd11cedf02fb3642a05d8c7db4dcf1d6`. This report lands separately after work commit.
- Before r36 HEAD `e66314d93f498010ec6ca661d84a59a1178b0c18`: 50 ordinary/61 full, focused and disconnected-signal slider arms but no same-wiring unfocused control. After: 51 ordinary/62 full and focus-absence negative. **Calibration improved**; **depth unchanged**, **coverage unchanged as axis** (extra row is paired calibration negative), none harmed in finite replay.
- Constants changed: 50→51 ordinary, 61→62 full, `--no-focus` expected exit2, value5 after both, receipts[], Label Value5. No rendered/pointer UI, physical keyboard/timing, OS window focus, accessibility, production or generic slider assurance; no engine/editor/seeded control edits, publishing, push or merge.

## SHONEN
- [~] Decision/error table with cited source — `corpus/lessons/r37-hslider-focus-absence.md`; not independent promotion check.
- [~] End-to-end task and named non-author replay — `reports/r37-focus-verifier.md`, `corpus/lessons/r37-focus-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
