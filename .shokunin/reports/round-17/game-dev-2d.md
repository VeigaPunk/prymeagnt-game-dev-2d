# game-dev-2d — round 17 (probation) — HOLD

Claim attempted: diagnose and causally repair the intermittent scratch Linux/X11 export-path failure observed in Round 16 without weakening export verdicts. Axis targeted: **calibration**. Work/evidence commit `29c9b5b`; named non-author verifier `r17-export-verifier` (`openai-codex/gpt-6-luna`). **No move admitted. No runner change.**

## Evidence and decision
- Before: Round 16 author export exited 1 with `ERROR: Prepare Template: The given export path doesn't exist.` and zero products (`corpus/lessons/r16-export-adverse.json`), while parent and independent fresh retries passed. Round 17 scout, executor and critic compared outputs, preset/output paths and scratch layouts. Preset `export_path=""` is unchanged; the runner creates an empty out directory and supplies explicit target. The known nested-project warning occurs in both failed and successful exports. Adverse relative-root vs successful absolute-root paths belong to different runs; no single-variable intervention establishes a path cause.
- Bounded fresh real Godot exports by the leaves all succeeded; no original failure was reproduced. Executor refused to patch or add blind retries. Named non-author verifier independently exported a 73,703,800-byte Linux/X11 executable and reproduced the `Missing preset` rejection (exit 1 with exact invalid-preset diagnostic). Unmodified `--probe-failing` battery 33/33 PASS (`corpus/lessons/r17-battery-control.json`); 41 tracked fixture hashes unchanged. Successful controls do **not** resolve the earlier export failure. Evidence in `corpus/lessons/r17-export-path-hold.md` and `reports/r17-export-{scout,executor,critic,verifier}.md`. No leaf delegation, seeded fixture mutation, engine/editor source edit, publishing or push.

## Per-axis verdicts
- **Calibration unchanged / HOLD**: no causal fix or reliable reproduction; keep fail-closed positive export check and missing-preset negative unchanged.
- **Coverage unchanged**: no new fixture or game behavior.
- **Depth unchanged**: forensic comparison records unknowns but proves no new domain behavior.

No admission. Export-path failure cause remains open. No general export reliability or production readiness claim. Constants changed: none.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r17, including adverse HOLD; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — verifier reproduced controls, but causal repair not established; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
