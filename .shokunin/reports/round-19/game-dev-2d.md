# game-dev-2d — round 19

Work commit: `794bca52e2041905200a1f0cb18f848e69b6f863` (`git rev-parse HEAD` at report-write time, before this report file existed). Named non-author verifier: `r19-stream-verifier`.

## Work performed

- Loaded godspeed (`directive.md`) and shokunin (`SKILL.md`) before acting. Owned axes: depth, coverage, calibration. One axis-move: calibration, the scorecard's lowest unprobed diagnostic class (stdout/stderr attribution).
- Confirmed Godot 4.7.2 splits streams: `print` on stdout, `printerr` / `push_error` / `push_warning` on stderr. Parent scratch under `/tmp/gd-stream-probe`; scout re-ran the same split under `/tmp/stream_attr_scout_yw_860f1` (`reports/r19-stream-scout.md`).
- Dispatched 8 L2 lanes in one turn, each `rlm.spawn(..., model='xai/grok-4.5', thinking='low')` after `rlm.find_models` confirmed selector `xai/grok-4.5`: `r19-stream-scout`, `r19-stream-executor`, `r19-stream-critic`, `r19-hash-scout`, `r19-regression-scout`, `r19-fixture-scribe`, `r19-scope-sentinel`, `r19-claim-planner`.
- Landed `corpus/fixtures/stream_attribution_probe.gd` and `--probe-stream-attribution` plus `classify_streams` in `corpus/fixtures/run_battery.py`. `classify_process` was not edited (`reports/r19-stream-executor.md`).
- Critic showed concatenated `classify_process` false-admits the reject arm, and named a prefix-only hole in `classify_streams` (`reports/r19-stream-critic.md`). Parent closed that hole: any non-empty stderr line not in `allowed_stderr` rejects. Author re-run meta PASS at `corpus/live/runs/20261012T232054666461Z/stream-attribution-verdicts.json` (author evidence only).
- Named non-author `r19-stream-verifier` re-ran the after command and fault injection (`reports/r19-stream-verifier.md`).

## Landed changes

- `corpus/fixtures/stream_attribution_probe.gd` — SceneTree probe; always prints the stdout marker; `--stderr-unrelated` adds one `printerr`; both arms `quit(0)`. Carried by `794bca52e2041905200a1f0cb18f848e69b6f863`. LOG.md round-19 entry.
- `corpus/fixtures/run_battery.py` — opt-in `--probe-stream-attribution`, separate stdout/stderr capture, `classify_streams`. `classify_process` body equal to HEAD `fa31bef6c02b3ffb1cd2f8b98d60f4375f8ad776`. Same commit. LOG.md round-19 entry.
- `corpus/lessons/r19-stream-attribution.md`, `corpus/lessons/r19-stream-verifier.json`, `corpus/lessons/r19-fault-regression.json`, `corpus/README.md` index lines, `SCORECARD.md`, `LOG.md`, and leaf reports `reports/r19-{stream-scout,stream-executor,stream-critic,stream-verifier,hash-scout,regression-scout,scope-sentinel,claim-planner}.md`. Same commit.

## Before → after measurements

- Before, at `fa31bef6c02b3ffb1cd2f8b98d60f4375f8ad776`: `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error` → 33/33 PASS, no stream-attribution case (scorecard r11 measurement; regression scout listed the same 33 ordinary names in `reports/r19-regression-scout.md`). This round did not re-run that before command as a separate full battery; the after command includes those flags and the verifier counted the same 33 ordinary names all PASS.
- After, measured by non-author `r19-stream-verifier` on the uncommitted runner that became `794bca52e2041905200a1f0cb18f848e69b6f863`: `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch --probe-godot-error --probe-stream-attribution` → exit 0, meta PASS, **42/42** (33 ordinary + 2 mutants + 6 existing opt-in + 1 `probe_stream_attribution`). Raw `corpus/lessons/r19-stream-verifier.json`.
- Stream pair in that run's `stream-attribution-verdicts.json`: both arms `res://stream_attribution_probe.gd`, both exit 0. Accept inner true, stdout marker `STREAM_STDOUT: expected attribution marker`, stderr empty. Reject inner false, stderr exactly `STREAM_STDERR: unrelated attribution diagnostic`. Meta PASS. Console `FAIL stream_reject` is the expected inner print, not a battery failure.
- Fault injection, separate: `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --fault-injection` → exit 0, meta PASS (`corpus/lessons/r19-fault-regression.json`).
- Hash check: verifier SHA-256 of `corpus/fixtures/` excluding `live` differed from the scout BEFORE list only in `run_battery.py`. New fixture hash stable after it appeared. `classify_process` body unchanged versus HEAD.

## Verdicts

- calibration: **improved** — one paired real Godot 4.7.2 stdout/stderr attribution accept/reject, identical exit, separate streams, named non-author replay.
- depth: **unchanged** — no new mechanic fixture; ordinary case list untouched.
- coverage: **unchanged** — prior 33 ordinary outcomes still PASS; no new product surface.
- none harmed in this finite replay.

Not claimed: crash-exit classification, process-tree timeout, export reliability, rendered output, or ordinary `run_process` stream separation (still concatenated). The r16 intermittent export-path failure remains unresolved even though this replay's export rows passed.

Constants: stdout marker `STREAM_STDOUT: expected attribution marker`; stderr diagnostic `STREAM_STDERR: unrelated attribution diagnostic`; user flag `--stderr-unrelated`; both arms quit 0; subprocess bound 8 seconds. No engine/editor source edit, no publication, no push. No parent session was attached, so the completion `agent_message` to parent could not be delivered.

## SHONEN

- [~] Real decision tables/error patterns/checklists with cited sources — pointer: `corpus/lessons/r19-stream-attribution.md` and `reports/r19-stream-verifier.md` (stream split table). Box stays [~]: the non-author verifier checked the probe, not this probation box.
- [~] End-to-end domain task executed and logged; non-author verifier required — pointer: `r19-stream-verifier` replay 42/42 in `reports/r19-stream-verifier.md`, raw `corpus/lessons/r19-stream-verifier.json`, work commit `794bca52e2041905200a1f0cb18f848e69b6f863`. Not a promotion check.
- [ ] Instructions executable without oral context.
- [ ] No cross-domain bleed; PROVINCE remains accurate.
