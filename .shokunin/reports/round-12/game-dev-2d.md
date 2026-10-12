# game-dev-2d — round 12 (probation)

Claim: headless Godot `AudioStreamPlayer` for generated in-memory WAV enters playback and advances its observed position, while a same-assertion no-play control rejects it. Axis move: **coverage**. Work and raw evidence committed in `9fb606d`; named non-author verifier `r12-audio-reverify` (`openai-codex/gpt-6-luna`).

## Work performed
- Before: Round 11 had **27** ordinary feature/mutant cases and 33/33 with optional probes, no audio fixture. Round 12 added `audio_playback.gd` and two cases to the battery. It generates 44,100 bytes of 16-bit mono 22,050 Hz WAV data, attaches an `AudioStreamPlayer`, samples the position immediately after `play()` and after 12 process frames, and asserts in-tree, `is_playing()`, and >0.001 s advance. The no-play branch skips only `play()` and reaches the same assertion. The runner accepts only that negative's exact `ERROR: AUDIO ASSERTION FAILED` diagnostic.
- Wave 1 scout/executor/critic, wave 2 non-author verifier, wave 3 cleanup executor, wave 4 non-author re-verifier. The first non-author verifier found 35/35 functional PASS but placed **HOLD** because positive playback emitted `WARNING: 2 ObjectDB instances were leaked at exit` (not present in no-play); minimal verbose WAV scratch identified retained `AudioStreamWAV` and `AudioStreamPlaybackWAV`. Explicit stop/free and a four-frame drain did not resolve it. The adverse raw record remains committed as `corpus/lessons/r12-initial-hold.json` and explained by `reports/r12-audio-verifier.md`.
- The cleanup executor changed the post-stop/free drain **4 → 120 process frames**, without changing the 12-frame observation or suppressing warnings. Author replay 29/29 was warning-free (`corpus/lessons/r12-cleanup-author.json`). No leaf delegation, seeded fixture mutation, editor/engine source edit, push, or publishing.
- Independent re-verification: `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error` exited 0, **35/35 PASS** (`corpus/lessons/r12-battery-verifier.json`). Positive exit 0, `in_tree=true playing=true`, position `0.00580498855561 → 0.09868481010199`; no-play exit 2 at same assertion, `in_tree=true playing=false`, position `0.0 → 0.0`. Both audio raw outputs and two more direct positive runs had zero WARNING/ObjectDB lines. `--fault-injection` meta PASS (`corpus/lessons/r12-fault-regression.json`); all 38 tracked fixture hashes were unchanged before/after. Details in `corpus/lessons/r12-headless-audio.md` and `reports/r12-audio-reverify.md`.

## Before → after and per-axis verdicts
- **Coverage improved**: 27 → **29** ordinary feature/mutant cases, with independently observed headless playback state/position and a no-play control, while earlier cases remain passing.
- **Calibration unchanged**: case-scoped exact expected-negative diagnostic follows existing classifier policy; no new general diagnostic-classifier claim.
- **Depth unchanged**: a bounded lesson and adverse/repair evidence record the decision but do not claim a second axis move.

Admitted narrowly: one improved axis, no observed harmed axis. The 120-frame drain removed warnings in these finite replays but is not a general audio-resource guarantee. Playback-position bookkeeping is **not audible sound**, mixer/device quality, gameplay integration, asset rights, or production readiness.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r12; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — non-author HOLD then re-verification with committed raw JSON; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
