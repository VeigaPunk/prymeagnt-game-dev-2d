# game-dev-2d — round 36 — coverage

## Work performed
- Declared focused HSlider numeric action and signal coverage in LOG before eight wave-1 leaves. Work commit `847efb8bf748b657f56fe4f745392140844fec48`. Scratch measured real Godot 4.7.2: `Input.action_press` alone did not route; fresh `InputEventAction` via `Input.parse_input_event` drove an in-tree focused HSlider min0 max10 step1 initial5 by `ui_right` pressed/released then `ui_left` pressed/released. The connected case changes 5→6→5 and emits `[6,5]`, Label `Value 6` then `Value 5`; disconnected same actions retain both value changes but emit `[]`, Label stays `Value 5`, intended missing-signal exit2 only after both actions. GUI focus owner is checked before each action. No programmatic assignment as stimulus or manual signal emission. Executor's initial `Input.action_press` failure and undeclared `viewport` parse failure remain adverse scratch evidence.
- Named non-author `r36-slider-verifier` ran default-path full `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit0 **61/61 PASS** (50 ordinary +2 mutants +9 opt-ins). All prior r35 **59** `(verdict,actual_exit,signature)` triples unchanged; exactly two new PASS rows exit0/exit2. Raw byte-identical `corpus/lessons/r36-slider-verifier.json`, report `reports/r36-slider-verifier.md`. Separate fault run outer PASS with intentional inner timeout/unrelated-error FAIL (`r36-fault-verifier.json`). Scratch sabotage removing input-event parse failed connected state/signal and disconnected first transition, neither false-PASS; hashes stable.

## Landed changes and before → after
- LOG/SCORECARD, new `slider_adjust.gd`, runner two rows/classifier, lesson, wave and verifier reports/raw: `847efb8bf748b657f56fe4f745392140844fec48`. This report lands separately after the work commit.
- Before r35 HEAD `de4d3410ee1e41eda5178f4b73eb217c979c8979`: 48 ordinary/59 full, programmatically updated TextureProgressBar gauge but no focused numeric HSlider input. After: 50 ordinary/61 full and paired connected/disconnected keyboard-action numeric slider cases. **Coverage improved**, **depth unchanged**, **calibration unchanged as axis**, none harmed in finite replay.
- Constants changed: 48→50 ordinary, 59→61 full, min0/max10/step1/value5, expected 6→5, receipts `[6,5]`, disconnected expected exit2. No rendered or pointer input, physical timing/keyboard, accessibility, production UI, general slider correctness, engine/editor/seeded control edits, publishing, push or merge.

## SHONEN
- [~] Decision/error table with cited source — `corpus/lessons/r36-hslider-focused-input.md`; not independent promotion check.
- [~] End-to-end task and named non-author replay — `reports/r36-slider-verifier.md`, `corpus/lessons/r36-slider-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
