# game-dev-2d — round 27 — coverage

## Work performed
- Declared headless in-tree Button action → pressed signal → Label update with disconnected control in `.shokunin/game-dev-2d/LOG.md` before dispatch. Eight leaf slots settled; **four errored `Child worker unreachable`** (scout, baseline scout, mutation reviewer, simplifier), no assigned reports; their scratch excluded. Work commit `6dfbf56795ec5f00778ec3dc7bb36e788a3084ab`.
- Added `corpus/fixtures/button_activation.gd` and two ordinary rows plus exact expected diagnostic in `run_battery.py`. Executor author replay 41/41 PASS after correcting first diagnostic punctuation mismatch (`reports/r27-button-executor.md`). Critic's scratch direct receiver callback spoofed disconnected final state; actual fixture has no direct call/manual signal emission, so admission excludes arbitrary edited-fixture resistance (`reports/r27-button-critic.md`).
- Named fresh non-author `r27-button-verifier` independently ran `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution --probe-crash-exit --probe-timeout`: exit 0, **52/52 PASS** (41 ordinary +2 mutants +9 opt-in), raw `corpus/lessons/r27-button-verifier.json`, leaf `reports/r27-button-verifier.md`. Separate `--fault-injection` top-level meta PASS with intentional inner FAILs raw `r27-fault-verifier.json`; tracked hashes unchanged during verifier.

## Landed changes
- LOG/SCORECARD, Button fixture/runner, cited lesson, four available wave-1 reports (four missing failed leaves), named verifier report and two raw JSON: `6dfbf56795ec5f00778ec3dc7bb36e788a3084ab`. This report lands after that work commit.

## Before → after measurements
- Immutable pre-change `a25ca36abcf4ae92ea42549d5cb464e2988761d9`: 39 ordinary CASES, r26 full 50/50; existing HUD emits custom signal directly, not Button input. At `6dfbf56795ec5f00778ec3dc7bb36e788a3084ab`, named verifier command above 52/52, prior 50 unchanged. Positive: in-tree Button+Label initial `Ready`, focused `ui_accept` pressed/released via `root.push_input`, one `pressed` receipt, final `Activated`, exit0. Disconnected: same action, zero receipts/text Ready, exit2 on intended final assertion, not setup.
- Verdicts: **coverage improved** for actual tracked headless Button action/signal/Label path; **depth unchanged**, **calibration unchanged**, none harmed in finite replay. Critic's injected direct-callback spoof passes disconnected arm; no arbitrary mutation resistance claim. No pointer hit-testing, rendered UI, accessibility or production scene claim.
- Constants: action `ui_accept`, initial `Ready`, final `Activated`, expected callback count 1. No engine/editor or seeded control mutation, publishing, push, merge.

## SHONEN
- [~] Real decision/error table with cited source — `corpus/lessons/r27-button-action.md`; verifier did not review probation box.
- [~] End-to-end task and named non-author replay — `reports/r27-button-verifier.md`, `corpus/lessons/r27-button-verifier.json`; not promotion check.
- [ ] Executable instructions without oral context — not independently checked.
- [ ] No cross-domain bleed, PROVINCE accurate — not independently checked.
