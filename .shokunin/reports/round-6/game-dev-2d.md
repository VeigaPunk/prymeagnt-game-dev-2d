# game-dev-2d — round 6 (probation)

Claim: scratch Godot Linux/X11 export operation succeeds and a missing preset fails specifically without output; retain 23 prior cases. One axis-move: **coverage**. Work commit `ff0a333`, scratch-bookkeeping corrections `11c2197`, `a83d5bb`, `26eb601`, scorecard `70416ed5df6817983796781023f244cb57cbec49`. Named final non-author verifier `r6-export-verifier-final` (`openai-codex/gpt-6-luna`).

## Work performed
- Wave 1 scout/executor/critic `.shokunin/game-dev-2d/reports/r6-export-scout.md`, `r6-export-executor.md`, `r6-export-critic.md`. Wave 2 `r6-export-verifier` independently found that the first negative scratch copy inherited `.pck` and `.sh` sidecars despite absent executable; HOLD in `r6-export-verifier.md`. Orchestrator corrected runner to exclude prior `out`, require empty out before export, inventory/delete all products, and require entire negative out remain empty. Extra named final non-author `r6-export-verifier-final` independently replayed corrected runner (`r6-export-verifier-final.md`). All leaves settled without delegation.
- Added `corpus/fixtures/export_presets.cfg` Linux/X11 preset and actual `godot --headless --path <scratch> --export-debug Linux/X11 <scratch>/out/fixture.x86_64` branch to `run_battery.py` (`ff0a333`). Positive generated 73,703,800-byte executable SHA-256 `1a291d3d15e4180b60b0af96cf6458f11fe143636d76575ddf1e23d1a3f24f2e`, plus `.pck` and `.sh`; runner inventoried and deleted all scratch products. Negative separate scratch selects nonexistent preset, exit 1 exact `Invalid export preset name`, no output file. Nothing published.
- Final independent command `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → exit 0, **25/25 PASS** in committed `corpus/lessons/r6-export-verifier.json`; prior 23 retained, output dirs empty after. Verifier hash-checked 35 prior tracked fixtures unchanged. Raw positive has a nested-project warning: `res://controls/project.godot` is skipped by export scanner.
- Initial work commit accidentally staged 180 disposable live verifier scratch files. `.gitignore` corrected (`11c2197`), tracked scratch removed in `a83d5bb`, correction logged (`26eb601`). `git ls-files .shokunin/game-dev-2d/corpus/live` now lists only `.gitignore`; no binary was committed/pushed. Raw independent verdict remains committed at `corpus/lessons/r6-export-verifier.json`.

## Landed changes
- Round declaration, fixture preset, runner, raw record, bounded decision table in `ff0a333`; scratch bookkeeping correction commits above; scorecard evidence in `70416ed5df6817983796781023f244cb57cbec49`. All attributed `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. This report and five scoped leaf reports land last.

## Before → after measurements and per-axis verdicts
- **Coverage improved**: export operation cases 0 at `5251bcd` → 2 at `70416ed5df6817983796781023f244cb57cbec49`, counted from runner `CASES`; command above → 25/25 final independent PASS in `corpus/lessons/r6-export-verifier.json`, versus 23/23 at `corpus/lessons/r5-animation-verifier.json`. Positive actually exported and hashed a scratch executable; negative rejected a missing preset with full output-dir check.
- **Depth unchanged**: bounded table `corpus/lessons/r6-export-headless.md`, no independent depth move.
- **Calibration unchanged**: local Godot 4.7.2 Linux/X11 fixture export only. Nested controls project was skipped; no claim of exported app launch, complete fixture packaging, production project readiness, cross-platform availability, publishing, distribution rights or asset clearance.

Admitted narrowly: coverage improved, no harmed axis. Initial verifier HOLD and transient tracked-scratch defect are recorded, not erased. No promotion.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons r1–r6; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — `r6-export-verifier-final`, committed raw `corpus/lessons/r6-export-verifier.json`; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson commands; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
