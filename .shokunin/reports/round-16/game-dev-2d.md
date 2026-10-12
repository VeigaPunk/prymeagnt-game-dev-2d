# game-dev-2d — round 16 (probation)

Claim: existing headless health-gauge fixture distinguishes lower/upper clamped values and omits duplicate `value_changed` callback when repeated out-of-range input clamps to current maximum. One axis-move: **depth**. Work/raw evidence committed `0a5fc5a`; named non-author verifier `r16-clamp-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Before: r15 established only health=35 producing value 35 and one receipt, with 33 ordinary feature/mutant records and 40/40 combined. R16 retains the original setup/first assertion and disconnected negative, then emits -10, 140, 140. The fixture samples actual gauge value immediately after each emission: 0, 100, 100; checks exact ordered `value_changed` receipts `[35,0,100]`, so repeated 140 emits no fourth callback. Range 0..100, initial 100. The runner changed only the positive case signature; no new case or classifier rule.
- Scout/executor/critic wave then named non-author verifier. Critic initially saw only aggregate receipts/final value; parent requested per-emission value snapshots, executor added them. Executor's full author `--probe-failing` run **failed** on an unrelated export-path error (`ERROR: Prepare Template: The given export path doesn't exist.`) while both gauge cases passed. Raw adverse record `corpus/lessons/r16-export-adverse.json`; parent fresh retry 33/33 PASS in `r16-parent-retry.json`. Export failure root cause is **unresolved**, not erased by subsequent passes. No leaf delegation, seeded fixture mutation, engine/editor source edit, publishing or push.
- Named non-author verifier fresh combined `--probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-audio-warning` exit 0, **40/40 PASS** (31 base + 2 scratch mutants + 7 opt-in), `corpus/lessons/r16-clamp-verifier.json`. Disconnected gauge exits 2 at original first assertion, actual value 100/empty receipts before clamp branch. Scratch-only changing expected low value 0→1 or shortening receipt list independently made positive fail at clamp assertion. `--fault-injection` meta PASS (`corpus/lessons/r16-fault-regression.json`). Export readiness and launch passed this time; no general reliability inference. Verifier fixture SHA-256 manifest unchanged. See `corpus/lessons/r16-gauge-clamp.md`, `reports/r16-clamp-verifier.md`.

## Before → after and per-axis verdicts
- **Depth improved**: existing gauge now verifies two range boundaries, ordered receipts and no extra callback for same-current repeat in a synchronous headless process.
- **Coverage unchanged**: same 33 ordinary records and existing gauge behavior category.
- **Calibration unchanged**: no classifier rule changed. Intermittent export-path failure remains an adverse reliability observation; do not claim export is stable.

Admitted narrowly: one improved axis, no demonstrated gauge regression. No rendered gauge, production health integration, asynchronous/re-entrant suppression, or dependable export-success claim.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r16; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named verifier replay, scratch sabotage and adverse export raw committed; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
