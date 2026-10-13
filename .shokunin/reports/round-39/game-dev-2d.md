# game-dev-2d — round 39 — depth

## Work performed
- Declared deliberate second fresh HSlider `ui_right` press history in LOG before eight wave-1 leaves. Work commit `1f983f9ce670a9f90cc5e213ed641b35cdb74141`. Real Godot 4.7.2 focused HSlider min0 max10 step1 initial5: first right press→6, second distinct fresh right press (without release)→7, right release holds7, two left press/release pairs→6 then5; each event followed by one frame. Connected cumulative receipts `[6,7,6,5]`, signal-driven Labels 6→7→6→5. Paired disconnected same numeric seven-edge history, receipts[], Label Value5, intended exit2 only after all edges. Focus owner checked before each. Author first full run 63/64 failed only from missing exact negative classifier; raw failed telemetry retained and corrected before final author 64/64.
- Named non-author `r39-repeat-verifier` default-path full `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit0 **64/64 PASS** (53 ordinary +2 mutants +9 opt-ins); all prior r38 **62** `(case,verdict,actual_exit,signature)` rows unchanged, two new PASS rows exits0/2. Byte-identical `corpus/lessons/r39-repeat-verifier.json`, report `reports/r39-repeat-verifier.md`; separate fault outer PASS with intentional inner hang/unrelated-error FAIL (`r39-fault-verifier.json`). Verifier's first sabotage mistakenly removed event and loop entry, failed at right release; corrected scratch preserves all seven checks but omits only second dispatch, failing specific second right-press assertion (actual6/[6] vs expected7/[6,7]). Tracked hashes stable.

## Landed changes and before → after
- LOG/SCORECARD, `slider_adjust.gd` repeat mode, runner paired rows/classifier, lesson, wave and verifier reports/raw: `1f983f9ce670a9f90cc5e213ed641b35cdb74141`. This report lands separately after work commit.
- Before r38 HEAD `992e2df`: 51 ordinary/62 full with one right press/release and one left press/release. After: 53 ordinary/64 full with deliberate second right press and two left press/release pairs in connected/disconnected arms. **Depth improved**; **coverage unchanged as axis** (new pair deepens same slider), **calibration unchanged**, none harmed in finite replay.
- Constants changed 51→53 ordinary, 62→64 full, repeat-right values 6,7,7,6,6,5,5, final receipts `[6,7,6,5]`, disconnected expected exit2. No OS auto-repeat, physical timing/keyboard, rendered/pointer UI, accessibility, production or generic slider claim; no engine/editor/seeded control edits, publishing, push or merge.

## SHONEN
- [~] Decision/error table with cited source — `corpus/lessons/r39-hslider-deliberate-second-press.md`; not independent promotion check.
- [~] End-to-end task and named non-author replay — `reports/r39-repeat-verifier.md`, `corpus/lessons/r39-repeat-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
