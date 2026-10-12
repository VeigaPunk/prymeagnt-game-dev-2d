# game-dev-2d — round 10 (probation)

Claim: a scratch Linux/X11 exported executable directly starts one finite scripted scene event, while a separately exported clean control with the event print removed fails the same assertion. One axis-move: **coverage**. Work commits `7670476f7d7d9336b296669aca28587bcb9012dd`, `74e47211b48ac0e3ac84b974c560107d53c084f6`. Named non-author verifier `r10-launch-verifier` (`openai-codex/gpt-6-luna`).

## Work performed
- Before: r6/r9 exported a scratch artifact then deleted it, without direct launch; r9 had 27 original/mutant cases plus four classifier probes. Wave 1 scout/executor/critic, wave 2 verifier; reports `.shokunin/game-dev-2d/reports/r10-launch-*.md`. Critic's early HOLD saw only unfinished flag. An early missing-main-scene draft hit timeout-output bytes/string TypeError and was discarded; executor report retains this adverse evidence. Corrected control keeps the same configured scratch main scene/script and removes only the event print. No leaf delegation.
- Opt-in `--probe-export-launch` adds no seeded fixture files; runner creates two independent scratch projects, main-scene GDScript and project setting, exports each Linux/X11, directly executes `<out>/fixture-launch.x86_64 --headless` with cwd `<variant>/out` containing only export products, bounds launch at 5s, checks exactly one `EXPORT_LAUNCH_READY scene=fixture` line in positive and clean exit 0 without token in control, and deletes generated products after hashing/inventory. Both variants share the same token predicate; separate PCK SHA-256 digests prove distinct packages. Test does not invoke Godot editor as a substitute for exported binary.
- Independent `python .shokunin/game-dev-2d/corpus/fixtures/run_battery.py --probe-failing --probe-unrelated-error --probe-export-launch` → exit 0, **32/32 PASS** in committed `corpus/lessons/r10-battery-verifier.json`; paired raw command/output/hash/cleanup in `corpus/lessons/r10-launch-verifier.json`. Both exports exit 0, executable template 73,703,800 B, positive PCK 28,020 B vs control 27,956 B with distinct hashes. Both direct launches exit 0/no timeout or unexpected ERROR; positive exact token once, control none, all products deleted. Verifier scratch removal of positive print made meta FAIL / runner exit 1. Independent `--fault-injection` meta PASS in `corpus/lessons/r10-fault-regression.json`; 37 tracked fixture/runner paths hash-identical before/after verifier replay.

## Landed changes
- Declaration/closure, runner, independent raw JSON and bounded lesson in `7670476f7d7d9336b296669aca28587bcb9012dd`; scorecard evidence hash in `74e47211b48ac0e3ac84b974c560107d53c084f6`. Both commits use `game-dev-2d-shokunin <game-dev-2d@shokunin.local>`. Leaf reports and this report land last.

## Before → after measurements and per-axis verdicts
- **Coverage improved**: from 0 exported-app launches at r9 `72222e1` to one synthetic headless startup event with a same-assertion no-event control and independent 32/32 at `74e47211b48ac0e3ac84b974c560107d53c084f6`. This is a scratch fixture, not the production project, rendering, GUI, other platforms or publishing.
- **Depth unchanged**: `corpus/lessons/r10-export-launch.md` records bounded decisions, no separate depth move.
- **Calibration unchanged**: prior diagnostic and fault probes pass; no new general classifier threshold.

Admitted: coverage improved, no harmed axis. Exported executable startup was verified only on this host's Godot 4.7.2 Linux/X11 headless template.

## SHONEN
- [~] Real decision tables/error patterns/checklists with cited sources — corpus lessons through r10; no operator-appointed promotion review.
- [~] End-to-end domain task executed and logged — named verifier `r10-launch-verifier`, committed raw launch/battery JSON; promotion box remains unchecked.
- [~] Instructions executable without oral context — `corpus/README.md` and lesson command; promotion box remains unchecked.
- [~] No cross-domain bleed; province accurate — `.shokunin/game-dev-2d/PROVINCE.md`; no promotion review.
