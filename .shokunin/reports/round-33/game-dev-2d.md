# game-dev-2d — round 33 — depth

## Work performed
- Declared a CheckBox press-only/release-only state/receipt/Label depth claim in LOG before dispatch. Eight wave-1 leaves and named non-author verifier settled. Work commit `f9b13a674665f212ac3946d9a49181384fe6cd28`.
- Tracked fixture now asserts four after-frame checkpoints across two focused synthetic `ui_accept` press/release pairs: checked states `[false,true,true,false]`; connected `toggled(bool)` receipt states `[]`, `[true]`, `[true]`, `[true,false]`; Label Ready/On/On/Off. Disconnected control checks the same property states with no receipt and Label Ready at every edge, then exits2 intended final missing-signal assertion. Runner changed only positive CheckBox signature to name edge states; count remains 45 ordinary.
- Independent mutation reviewer and named verifier each omitted first release in disposable scratch, retained release1 assertion; setup and press1 passed, exit2 intended release-only state expected checked=true/got=false. No tracked sabotage switch.
- Named non-author `r33-checkbox-edge-verifier` ran full default-path `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit0 **56/56 PASS** (45 ordinary +2 mutants +9 opt-in). All 54 prior non-CheckBox verdict/actual_exit/signature triples unchanged; CheckBox PASS/exits preserved, positive edge signature intentionally changed, disconnected unchanged. The verifier report initially counted 45 signature-bearing non-CheckBox cases instead of all 54 including nine no-signature probe summaries; parent checked raw JSON and corrected report. Byte-identical raw `corpus/lessons/r33-checkbox-edge-verifier.json`, report `reports/r33-checkbox-edge-verifier.md`; separate fault-injection outer PASS with intentional inner adverse FAIL raw `r33-fault-verifier.json`. Source hashes stable during replay.

## Landed changes and before → after
- LOG/SCORECARD, CheckBox fixture/runner, lesson, wave and verifier reports/raw: `f9b13a674665f212ac3946d9a49181384fe6cd28`. This report lands separately after work commit.
- Before immutable r32 HEAD `11ab08294c27dfdc7e9d18878f84c16f63c431e1`: 45 ordinary/56 full, CheckBox state+signal checked after complete pairs only. After: still 45/56 with four per-edge state/receipt/Label checkpoints, missing-first-release caught at release1. **Depth improved** for bounded synthetic headless UI; **coverage unchanged**, **calibration unchanged**, none harmed in finite replay. No pointer/rendered UI, physical timing, accessibility, production behavior or arbitrary mutation-proof claim.
- Constants changed: CheckBox expected edge states `[false,true,true,false]`, receipt sequence `[]/[true]/[true]/[true,false]`, Labels Ready/On/On/Off; counts unchanged. No engine/editor or seeded control mutation, publishing, push, merge.

## SHONEN
- [~] Decision/error table with cited source — `corpus/lessons/r33-checkbox-edges.md`; not independent promotion check.
- [~] End-to-end task and named non-author replay — `reports/r33-checkbox-edge-verifier.md`, `corpus/lessons/r33-checkbox-edge-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
