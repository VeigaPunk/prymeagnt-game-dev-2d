# game-dev-2d — round 30 — depth

## Work performed
- Declared a two-action press-only/release-only headless Button depth claim before dispatch in LOG. Eight wave-1 leaves and named non-author verifier settled. Work commit `5485eb5adced01cbf119b734dc7b1fda543d1161`.
- Split the fixture's focused synthetic `ui_accept` actions across separate press/release events and awaited frames. Post-edge receipts `[0,1,1,2]`, Label texts `Ready`, `Activated 1`, `Activated 1`, `Activated 2`; focused setup precondition and release1 focus check retained. Disconnected and no-focus controls fail at intended release1 with zero/Ready. Runner changes only three Button signatures; count remains 42 ordinary.
- Mutation reviewer and named verifier each used disposable scratch to omit first release while retaining assertion: exit2 intended release1 with setup and press1 passing, zero receipts/Ready. No tracked sabotage flag.
- Named non-author `r30-edge-verifier` ran full default-path `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit0, **53/53 PASS** (42 ordinary +2 mutants +9 opt-in); all prior 50 non-Button verdict/exit/signature triples identical, three Button PASS/exits preserved with intended edge signatures. Byte-identical raw `corpus/lessons/r30-edge-verifier.json`, report `reports/r30-edge-verifier.md`; separate fault-injection outer PASS with intentional inner adverse FAIL raw `r30-fault-verifier.json`. Fixture/runner hashes unchanged through replay.

## Landed changes and before → after
- LOG/SCORECARD, Button fixture and runner, lesson, wave and verifier reports/raw: `5485eb5adced01cbf119b734dc7b1fda543d1161`. This report lands separately after the work commit.
- Before immutable r29 HEAD `511b2493b1b06352e6b85215197af7f28976e3a2`: 42 ordinary/53 full, two complete-pair post-action states only; no tracked press-only assertions. After: still 42/53, four asserted post-edge states and scratch missing-release killed at release1. **Depth improved** for this bounded synthetic headless action route; **coverage unchanged**, **calibration unchanged**, none harmed in finite replay. Not pointer/physical timing, debounce, rendered UI, accessibility, production focus or arbitrary mutation-proof behavior.
- Constants changed: positive edge sequence receipts `[0,1,1,2]` and texts `Ready`/`Activated 1`/`Activated 1`/`Activated 2`; negative diagnostics renamed release1; ordinary/full counts unchanged. No engine/editor or seeded control mutation, publishing, push, merge.

## SHONEN
- [~] Decision/error table with cited source — `corpus/lessons/r30-button-edges.md`; not independent promotion check.
- [~] End-to-end task and named non-author replay — `reports/r30-edge-verifier.md`, `corpus/lessons/r30-edge-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
