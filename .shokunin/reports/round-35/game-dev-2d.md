# game-dev-2d — round 35 — calibration

## Work performed
- Declared paired ButtonGroup B-membership causal control in LOG before dispatch. Eight wave-1 leaves and named non-author verifier settled. Work commit `e31f7e58997be8cd617ff513681ba51bb614a7b2`.
- Added `--ungroup-b` fixture mode and one ordinary expected-negative runner case. A stays in ButtonGroup; B keeps toggle-mode but no group association. Both grouped and ungrouped arms start A selected and send identical focused B→A synthetic `ui_accept` press/release actions with the same `toggled(bool)` signal wiring. Grouped path selects one control at a time, callbacks `[A:false,B:true,B:false,A:true]`; ungrouped path has A/B true/true after **both** actions, callbacks `[B:true,A:true]`, Labels B then A, then exits2 intended non-exclusive diagnostic. An early executor draft fell through to grouped assertion after B; another lacked the negative diagnostic classifier. Both were corrected before final replay; failures preserved in executor scratch/report.
- Named non-author `r35-group-absence-verifier` full default-path `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit0 **59/59 PASS** (48 ordinary +2 mutants +9 opt-in), all prior r34 58 verdict/actual_exit/signature triples unchanged. Direct scratch checked actual membership grouped true/true vs ungrouped A true/B false and focus B then A before actions. A sabotage retaining B's membership in ungrouped mode fails intended after-B state assertion. Byte-identical raw `corpus/lessons/r35-group-absence-verifier.json`, report `reports/r35-group-absence-verifier.md`; separate fault-injection outer PASS with intentional inner adverse FAIL raw `r35-fault-verifier.json`. Source hashes stable during replay.

## Landed changes and before → after
- LOG/SCORECARD, ButtonGroup fixture/runner, lesson, wave and verifier reports/raw: `e31f7e58997be8cd617ff513681ba51bb614a7b2`. This report lands separately after the work commit.
- Before immutable r34 HEAD `4f83d1d8fdd51a86b16abf3bc0743bc8e77087fb`: 47 ordinary/58 full, grouped positive and disconnected consumer, no tracked B-ungrouped control. After: 48 ordinary/59 full and group-absence negative after both B→A actions. **Calibration improved** under bounded synthetic headless ButtonGroup input; **depth unchanged**, **coverage unchanged as axis** (new row is this calibration negative), none harmed in finite replay. No RadioButton class, pointer/rendered UI, physical timing, accessibility, production behavior or generic ButtonGroup guarantee.
- Constants changed: 47→48 ordinary, 58→59 full, new negative expected exit2 and ungrouped receipt sequence `[B:true,A:true]`. No engine/editor or seeded control mutation, publishing, push, merge.

## SHONEN
- [~] Decision/error table with cited source — `corpus/lessons/r35-button-group-absence.md`; not independent promotion check.
- [~] End-to-end task and named non-author replay — `reports/r35-group-absence-verifier.md`, `corpus/lessons/r35-group-absence-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
