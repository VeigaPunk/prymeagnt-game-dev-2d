# game-dev-2d — round 21 — calibration

## Work performed
- Declared the normal-exit versus externally SIGTERM-terminated real-Godot comparison before dispatch in `.shokunin/game-dev-2d/LOG.md` round 21. Eight wave-1 leaves, then named non-author verifier; one requested name collision and its unique replacement are recorded there. Work commit `2e4cfa7ffb31d59c634dce1b1085b3ebfb302cfb`.
- Added only opt-in `--probe-crash-exit` and `crash_exit_probe.gd` in `.shokunin/game-dev-2d/corpus/fixtures/`; ordinary CASES unchanged. Executor report `.shokunin/game-dev-2d/reports/r21-crash-executor.md`. Initial missing reject `expected_exit` caught by critic/parent and corrected before replay.
- Named non-author `r21-crash-verifier` executed `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit`: exit 0, **45/45 PASS** (35 ordinary +2 mutants +8 opt-in). Raw `.shokunin/game-dev-2d/corpus/lessons/r21-crash-verifier.json`, detail `r21-crash-detail.json`; separate `--fault-injection` meta PASS in `r21-fault-verifier.json`. Verifier report `reports/r21-crash-verifier.md`.

## Landed changes
- LOG, SCORECARD, new opt-in fixture and runner path, decision table lesson, eight wave-1 reports, verifier report, raw replay/fault JSON: work commit `2e4cfa7ffb31d59c634dce1b1085b3ebfb302cfb`. This report lands in a later report-only commit.

## Before → after measurements
- At baseline `8c9a20b17cf745381f9efde445e4545e87e8e8f0`: 35 ordinary CASES, r20 full default-path 44/44 PASS, no real signal-termination probe (`reports/r21-baseline-scout.md`). At `2e4cfa7ffb31d59c634dce1b1085b3ebfb302cfb` the command above: named independent replay 45/45 PASS; 44 prior rows remain PASS. Exact marker `CRASH_EXIT_PROBE: expected signature` and same `res://crash_exit_probe.gd` in both arms. Normal exit 1 classified true; marker observed while reject process live, SIGTERM sent, actual Python return -15, classified false, no error or remaining direct child. No separate signal-guard sabotage run.
- Verdicts: **calibration improved** for one Linux/Godot 4.7.2 direct-child SIGTERM contrast; **coverage unchanged** (35 ordinary), **depth unchanged** (no new mechanic). None harmed in finite replay. No spontaneous-crash, SIGKILL, other-platform, process-tree timeout, or export-reliability inference. R16 export intermittence and r20 relative-`--runs` exception remain open.
- Constants changed: expected normal exit 1, signal SIGTERM 15 / Python return -15, marker above, fixture hold timer 30s, marker deadline 8s, cleanup bound 3s. No engine/editor source or seeded controls mutated, publication, push, or merge.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — `corpus/lessons/r21-signal-exit.md`; verifier checked probe, not probation box.
- [~] End-to-end domain task executed/logged and named non-author `r21-crash-verifier` replayed raw artifacts; not a promotion check.
- [ ] Instructions executable without oral context — not separately checked by non-author.
- [ ] No cross-domain bleed; PROVINCE accurate — not separately checked by non-author.
