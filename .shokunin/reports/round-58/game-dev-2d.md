# game-dev-2d — round 58 — coverage

## Work performed
- Declared one coverage move before wave 1 in `.shokunin/game-dev-2d/LOG.md`: test saved JSON reopened by a separate Godot process, with missing-file negative. Baseline r57 work/report `0c2ce964`/`6eb4df76`, 72 ordinary /83 full. Work commit `ca7cd3ac986e39c1e4a205385225e630a73bc48e`.
- Eight disjoint wave-1 leaf reports at `.shokunin/game-dev-2d/reports/r58-process-*.md` (scout, executor, critic, reviewer, simplifier, scribe, baseline, boundary); none delegated or committed. Scratch probes showed distinct PIDs and XDG/project-identity dependence. Executor alone added `corpus/fixtures/save_process.gd` and runner rows/meta after causal scratch.
- Named non-author `r58-process-verifier` ran exact seven flags under Godot 4.7.2; **87/87 PASS**, all **83/83** prior r57 records match selected case/script/flags/exit/signature/verdict/error fields. Raw byte-identical copy `corpus/lessons/r58-process-non-author.json`; process artifact `corpus/lessons/r58-process-evidence-non-author.json`. Writer PID 3256826 exits 0, then read-only reader PID 3256864 exits 0 with identical run-local XDG/project/file path and structured values; missing-file PID 3256911 exits 2 with expected diagnostic. Separate fault raw `corpus/lessons/r58-process-fault-non-author.json` outer PASS with intentionally failing inner arms; wrong-value and preexisting-missing scratch sabotages reject early. Initial relative-XDG sabotage attempt is adverse, excluded. Runner and fixture hashes stable across non-author replay.

## Landed changes and before → after
- Work commit `ca7cd3ac986e39c1e4a205385225e630a73bc48e` includes LOG/SCORECARD, fixture, runner, checklist, nine leaf reports and three named raw receipts. This report lands in a separate last commit.
- Before: 72 ordinary/83 full, one-process save/load only. After: 76 ordinary/87 full, three process CASE rows plus one meta row; exact non-author command `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --godot godot --runs .shokunin/game-dev-2d/corpus/live/r58-process-verifier/full-runs --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout` (fresh run root on replay). **Coverage improved**, **depth unchanged**, **calibration unchanged**, no harm in finite clean replay. Admitted only for orderly headless two-process JSON reuse and missing-file rejection.
- Constants changed: ordinary72→76, full83→87, three Godot invocations with distinct PIDs and shared absolute run-local XDG, expected missing-file exit2. No crash/power-loss durability, fsync, atomicity, broad tamper detection, production persistence, cross-platform, engine/editor source, publishing, push or merge claim.

## SHONEN
- [~] Decision/error checklist with sources — `corpus/knowledge/2026-10-12-production-checklist.md`, `.shokunin/game-dev-2d/reports/r58-process-reviewer.md`; no independent promotion check.
- [~] End-to-end domain task and named non-author replay — `.shokunin/game-dev-2d/reports/r58-process-verifier.md` plus `corpus/lessons/r58-process-non-author.json`; no independent promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed/province accurate — not independently checked.
