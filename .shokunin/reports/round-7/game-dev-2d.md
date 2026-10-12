# game-dev-2d — round 7 (probation)

Claim: shared battery executor/classifier detects bounded hangs and unrelated engine ERROR alongside an expected negative signature without harming 25/25 existing cases. One axis-move: **calibration**. Work commits `8c9799e23dd590a435e3b3a2af3a80f7323db7eb`, `7e073a77cb798ca1e2926f4fe1eae50152e5d18b`. Named non-author verifier `r7-fault-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Wave 1 scout/executor/critic evidence `.shokunin/game-dev-2d/reports/r7-fault-scout.md`, `r7-fault-executor.md`, `r7-fault-critic.md`. Critic caught an early hardcoded inner-FAIL fault draft; executor replaced it with shared `run_process`/`classify_process` used by normal cases and isolated `--fault-injection`. Wave 2 named non-author verifier `r7-fault-verifier.md` independently reran both modes and sabotaged classifier in disposable scratch, confirming fault meta exit 1 when unrelated-error inner verdict is incorrectly PASS. No leaf delegation.
- Shared subprocess timeout/classifier in `corpus/fixtures/run_battery.py`: 0.25s injected hang yields actual_exit null/TIMEOUT and inner FAIL; clean expected exit-2 diagnostic remains inner PASS; same exit/signature plus unrelated `ERROR:` is inner FAIL. Known negative diagnostics use case-owned allowed ERROR lines and two mutants retain intended signatures (`8c9799e23dd590a435e3b3a2af3a80f7323db7eb`). No normal timeout constant changed: Godot script 8s, export 60s; fault-only 0.25s / 2s.
- Verifier command `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --fault-injection` → exit 0/meta PASS in committed `corpus/lessons/r7-fault-verifier.json` (0.296s reported); `--probe-failing` → exit 0, 25/25 PASS in `corpus/lessons/r7-normal-verifier.json`. All 35 prior tracked fixtures besides runner hash-identical; runner itself unchanged by verifier.

## Landed changes
- Round 7 declaration/closure, shared classifier, raw fault and normal replay, decision table in `8c9799e23dd590a435e3b3a2af3a80f7323db7eb`; scorecard hash binding in `7e073a77cb798ca1e2926f4fe1eae50152e5d18b`. Both commits use `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. This report and four scoped leaf reports land last.

## Before → after measurements and per-axis verdicts
- **Calibration improved**: at `57f2170` no fault-injection replay or shared unrelated-ERROR rejection; at `7e073a77cb798ca1e2926f4fe1eae50152e5d18b`, `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --fault-injection` → meta PASS with inner verdicts FAIL/PASS/FAIL as captured in `corpus/lessons/r7-fault-verifier.json`; scratch sabotage of shared classifier changes meta to FAIL. Detection is for these injected faults, not universal.
- **Coverage unchanged**: `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → 25/25 in `corpus/lessons/r7-normal-verifier.json`, same count as r6; no game feature cases added.
- **Depth unchanged**: bounded classification table in `corpus/lessons/r7-fault-classification.md`, no independent decision-table depth move.

Admitted: calibration improved, no harmed axis. Not a proof of every crash, process-tree hang, forged log or Godot version.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r7; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named verifier `r7-fault-verifier`, committed raw fault/normal JSON; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson commands; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
