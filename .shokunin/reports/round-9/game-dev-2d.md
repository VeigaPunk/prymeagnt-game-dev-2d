# game-dev-2d — round 9 (probation)

Claim: export and mutant special-case verdicts reject appended/same-line unrelated `ERROR:` text alongside real captured clean outputs, while expected invalid-preset and mutant diagnostics remain accepted. One axis-move: **calibration**. Work commits `1dcb28e9c7d203529ad566dfdd5553dd41f11d23`, `379bb04bcaff756b34a0ca1b793ebaadaa46a13e`. Named non-author verifier `r9-diagnostic-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Wave 1 scout/executor/critic, wave 2 verifier; reports `.shokunin/game-dev-2d/reports/r9-diagnostic-*.md`. Scout found no demonstrated false acceptance in existing export/mutant branches, so this is previously **untested** rejection, not a claimed pre-existing exploit. Critic flagged early draft self-validating exit, weak export marker, mutant probe bypass; corrected before verifier. No leaf delegation.
- `run_battery.py`: opt-in `--probe-unrelated-error` reclassifies captured real Godot outputs after appending an unrelated `ERROR:` and same-line prefix/suffix spoof (invalid preset: appended + suffix). Shared `classify_process` is called by export branches, and a factored `classify_mutant(candidate_output)` is used both for real mutant verdicts and modified-output checks. Invalid-preset CASES expected exit corrected **2→1**, the observed actual exit (prior special branch ignored expected_exit). Successful scratch export requires `[ DONE ]`/`savepack`, nonempty executable, and no unrelated errors; generated products are deleted. No extra Godot execution for the text modifications.
- Independent `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error` → exit 0, **27 original cases + four opt-in probes PASS**, raw committed `corpus/lessons/r9-diagnostic-verifier.json`. Each probe's clean classification is true and injected classifications false. Export executable 73,703,800 bytes (SHA-256 `1a291d3d15e4180b60b0af96cf6458f11fe143636d76575ddf1e23d1a3f24f2e`), products deleted; missing preset exit 1/1, empty output. Independent `--fault-injection` remains meta PASS in `corpus/lessons/r9-fault-regression.json`.
- Verifier disabled shared unrelated-error filtering in disposable `/tmp` runner copy, then reran opt-in command: all four probe meta verdicts FAIL, battery exit 1. This checks branch reuse rather than trusting hardcoded expected inner verdicts. All 37 tracked fixture/runner paths hash-identical before/after verifier replay.

## Landed changes
- Declaration/closure, runner, independent raw JSON and bounded lesson in `1dcb28e9c7d203529ad566dfdd5553dd41f11d23`; scorecard evidence hash in `379bb04bcaff756b34a0ca1b793ebaadaa46a13e`. Both commits use `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. Leaf reports and this report land last.

## Before → after measurements and per-axis verdicts
- **Calibration improved**: at r8 `aabd6a2`, no opt-in export/mutant unrelated-ERROR replay; at `379bb04bcaff756b34a0ca1b793ebaadaa46a13e`, four branch-faithful output classifier probes PASS with clean=true, injected=false and scratch sabotage FAIL. Valid expected negative lines remain accepted. This is **captured-output string editing**, not real Godot stderr fault emission or universal spoof resistance.
- **Coverage unchanged**: 27 original cases PASS, no new feature case; four extra verdict calibration records are not counted as game coverage.
- **Depth unchanged**: new `corpus/lessons/r9-diagnostic-calibration.md` bounds the decisions; no separate depth move.

Admitted: calibration improved, no harmed axis. Exported-app launch and production readiness remain unproved.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r9; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named verifier `r9-diagnostic-verifier`, committed raw JSON; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
