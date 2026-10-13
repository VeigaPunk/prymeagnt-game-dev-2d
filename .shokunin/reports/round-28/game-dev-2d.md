# game-dev-2d — round 28 — depth

## Work performed
- Declared repeated Button action with ordered per-step receipts and scratch missing-second-action control in `.shokunin/game-dev-2d/LOG.md` before dispatch. Eight wave-1 leaves, then named non-author verifier settled. Work commit `ed031b5bf07a54ed83fbe007f4982386ffdbf389`.
- Deepened only `corpus/fixtures/button_activation.gd` and runner's two existing signatures; ordinary CASES count stayed 41. Tracked source sends two frame-separated focused `ui_accept` press/release pairs, checking after each pair for `[1,2]` receipts and `Activated 1`/`Activated 2`; disconnected control fails first step. Initial tracked `--skip-second` draft removed after reviewer advice; executor report corrected, scratch-only sabotage used. Scout observed signal fires on **release**, so final tracked assertions are post-pair, not per-edge (`reports/r28-repeat-scout.md`, LOG).
- Named non-author `r28-repeat-verifier` ran `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit 0, **52/52 PASS** (41 ordinary +2 mutants +9 opt-in), raw `corpus/lessons/r28-repeat-verifier.json`, report `reports/r28-repeat-verifier.md`. Disposable scratch removal of only second action exited 2 on intended step2 assertion with receipt1/text Activated 1; no setup error. Separate fault injection top-level meta PASS with deliberate inner adverse FAIL raw `r28-fault-verifier.json`. Tracked hashes unchanged during replay.

## Landed changes
- LOG/SCORECARD, Button fixture/runner, cited lesson, eight leaf reports, named verifier report and raw JSON: `ed031b5bf07a54ed83fbe007f4982386ffdbf389`. This report lands separately after the work commit.

## Before → after measurements
- Pre-change immutable HEAD `f99d7abfb3597d05e4c69d60218482122d0c98ec`: 41 ordinary CASES, r27 full 52/52; Button positive one receipt and final Activated, no second-step assertion (`reports/r28-baseline-scout.md`). At `ed031b5bf07a54ed83fbe007f4982386ffdbf389`, full named verifier 52/52 with 50 non-button records unchanged in verdict/exit/signature; positive two post-pair states `[Activated 1,Activated 2]`, receipts `[1,2]`; scratch missing-second action fails step2. Baseline-scout initially sent an executor-like identity message; its assigned immutable baseline report later landed. Authorship not inferred from that message.
- Verdicts: **depth improved** for bounded repeated headless Button signal/Label sequence; **coverage unchanged** (41 ordinary), **calibration unchanged**, none harmed in finite replay. Tracked fixture does not assert each press/release edge; no pointer, debounce, rendered UI or arbitrary mutation-resistance claim.
- Constants: two complete focused `ui_accept` pairs, expected receipt counts `[1,2]`, labels `Activated 1`/`Activated 2`. No engine/editor or seeded control mutation, publishing, push, merge.

## SHONEN
- [~] Decision/error table with cited source — `corpus/lessons/r28-button-repeat.md`; verifier checked round, not probation box.
- [~] End-to-end task and named non-author replay — `reports/r28-repeat-verifier.md`, raw `corpus/lessons/r28-repeat-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
