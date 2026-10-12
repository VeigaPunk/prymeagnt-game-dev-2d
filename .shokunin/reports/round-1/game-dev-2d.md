# game-dev-2d — round 1 (probation)

Claim: “A scratch-copy Godot battery detects a broken scene route and records machine-readable PASS/FAIL verdicts for the seeded fixtures without modifying them.” One axis-move: **coverage**. Work commit: `4468c15740ecbf7c53340cb8c85023df2fd35177`; verifier/measurement commit: `188188859b48beec707eadc771ffaed3ad8bc9ab`.

## Work performed
- Added serial scratch-copy Godot runner (`.shokunin/game-dev-2d/corpus/fixtures/run_battery.py`, commit `4468c15740ecbf7c53340cb8c85023df2fd35177`). It records command outcomes and signatures in JSON; `--probe-failing` changes only scratch `scene_b.tscn`.
- Documented sourced decision/error tables and agent checklist (`.shokunin/game-dev-2d/corpus/lessons/r1-headless-verification.md`, same commit). Initial missing-root-scene and one-frame scene-readiness errors are retained in `r1-initial.json`; scratch-only repairs produced `r1-passing.json`.
- Named non-author verifier `game-dev-2d-r1-verifier`, model `openai-codex/gpt-6-luna`, independently reran `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing`: exit 0, 15/15 PASS, mutant exit 2 with `chain incomplete`, no seed edits or defects; verifier message in this session. Verifier is **not** an operator-appointed promotion reviewer.

## Landed changes
- `.shokunin/game-dev-2d/LOG.md` round-1 entry and battery/evidence in `4468c15740ecbf7c53340cb8c85023df2fd35177`; independent verification and axis measurement in `188188859b48beec707eadc771ffaed3ad8bc9ab`.

## Before → after measurements
- Coverage: `git ls-tree -r --name-only 87c49620 .shokunin/game-dev-2d/corpus/fixtures | wc -l` → 29 seeds, no battery. `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing` → 15/15 PASS at `188188859b48beec707eadc771ffaed3ad8bc9ab`; first unadjusted execution 8/15 PASS (`corpus/lessons/r1-initial.json`) versus repaired 15/15 (`corpus/lessons/r1-passing.json`). Mutant exit 2 and `chain incomplete` is intentionally classified as detected only after the positive baseline passes. **Improved**.
- Depth: mint had no decision table/error-pattern checklist; `test -f .shokunin/game-dev-2d/corpus/lessons/r1-headless-verification.md` → true at `188188859b48beec707eadc771ffaed3ad8bc9ab`; sources and observed patterns are cited there. **Improved**.
- Calibration: `git show 188188859b48beec707eadc771ffaed3ad8bc9ab:.shokunin/game-dev-2d/corpus/knowledge/2026-10-12-production-checklist.md` still lists camera/UI/levels/juice/export as unprobed; no claim to those systems. **Unchanged**.

Admit: at least one axis improved, none harmed. This tests seeded script/scene/input/physics flow, **not** full 2D production or export readiness. Scores remain unassigned without a quality rubric; raw case counts are not scores.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — `.shokunin/game-dev-2d/corpus/lessons/r1-headless-verification.md`; probation box remains unchecked pending operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — `.shokunin/game-dev-2d/corpus/lessons/r1-passing.json`; named verifier above independently reran it, but did not approve promotion.
- [~] Instructions executable without oral context — `.shokunin/game-dev-2d/corpus/README.md` and lesson checklist; not checked.
- [~] No cross-domain bleed and accurate province — `.shokunin/game-dev-2d/PROVINCE.md`; no source or engine edits; not checked.
