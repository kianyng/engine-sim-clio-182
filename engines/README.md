# Engine revisions

This directory stores stable, named engine revisions so the active development file is not the only copy of a working state.

## Revision policy

- `reference/` contains known-good baselines and subsystem milestones.
- `stock/` will contain the final stock Clio 182 / F4R 738 files.
- `experiments/` can contain unstable test files.

## Current planned revisions

| Revision | Purpose | Status |
|---|---|---|
| rA | no-throttle-start baseline | active baseline |
| rB | locked hard geometry | in progress |
| rC | cylinder head correlation | planned |
| rD | camshaft/dephaser variants | planned |
| rE | intake and exhaust correlation | planned |
| rF | final stock F4R 738 | planned |

The current active script remains `clio182./clio182.mr` until a final release is ready.
