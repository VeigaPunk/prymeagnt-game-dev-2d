# game-dev-2d — round 14 (probation)

Claim: the production battery rejects `audio_playback` when captured Godot output contains the known ObjectDB leaked-instances warning, while accepting warning-free audio and retaining unrelated export warning acceptance. One axis-move: **calibration**. Work/evidence committed `ba3293a`; named non-author verifier `r14-warning-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Before: Round 12 initial HOLD captured a positive audio process with exit 0 and correct playback signature **plus** `WARNING: 2 ObjectDB instances were leaked at exit (run with `--verbose` for details).`, yet the shared classifier counted it PASS. Round 13 had 31 ordinary cases and 37/37 combined. The runner now routes only positive `audio_playback` through `classify_audio_process`, which retains shared exit/signature/ERROR/parse checks and additionally rejects a full-line positive-integer ObjectDB leak warning, including the observed optional verbose suffix. Export cases retain the generic classifier and their nested-project warning.
- Optional `--probe-audio-warning` reclassifies R12's committed actual Godot initial-HOLD and clean captured outputs through the **production** audio classifier. It requires leaked FAIL, clean PASS and the expected warning presence/absence. First executor regex failed to match verbose suffix and second misplaced punctuation; critic and parent identified defects and executor corrected them before passing author run. No new real leak emission is claimed. Leaf reports retain the adverse sequence; no leaf delegation, seeded fixture mutation, engine/editor source edits, publishing or push.
- Independent verifier combined `--probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-audio-warning` exit 0, **38/38 PASS**: 31 ordinary plus seven meta/probe records (`corpus/lessons/r14-warning-verifier.json`). Captured R12 leaked audio with valid exit/signature now FAIL; captured and live clean audio PASS. Both export cases PASS despite nested-project WARNING. `--fault-injection` meta PASS (`corpus/lessons/r14-fault-regression.json`). Scratch-only disabling the new reject clause made probe and command FAIL; an unrelated warning on clean audio remained PASS; matching ObjectDB warning with count 3 made it FAIL. Verifier hashed 40 tracked fixture paths unchanged. See `corpus/lessons/r14-audio-leak-warning.md`, `reports/r14-warning-verifier.md`.

## Before → after and per-axis verdicts
- **Calibration improved**: actual R12 leaked warning no longer receives a false PASS while clean audio and unrelated export warnings retain PASS. Scope is this grammar in positive audio output, not every warning or leak form.
- **Coverage unchanged**: 31 ordinary cases retained; this is classifier/probe evidence rather than new game-feature coverage.
- **Depth unchanged**: lesson records boundaries, no second move asserted.

Admitted: one improved axis, no observed harmed axis. The Round 14 adversarial leak sample is captured from R12 real Godot output, **not** newly emitted by Godot this round. No audible sound, production audio, or general leak-freedom claim.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r14; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — non-author paired-output replay and counterfactual, raw evidence committed; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
