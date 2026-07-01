# Renault Clio 182 F4R 738 - Engine Simulator CE

A research-backed Engine Simulator Community Edition project for the Renault Clio Renaultsport 182 F4R 738 engine.

The goal is not just to make a script that reaches 182 hp. The goal is to build a maintainable reference project where every important `.mr` value is either:

1. traceable to a real F4R / Clio 182 source,
2. derived from real geometry, or
3. clearly marked as a simulator correlation value.

## Current status

The current working script is:

```text
clio182./clio182.mr
```

That file is still an active development baseline. It should not yet be treated as a final stock F4R simulation.

## Key targets

| Target | Value |
|---|---:|
| Engine | Renault F4R 738 |
| Configuration | 2.0L naturally aspirated inline-4, DOHC, 16v |
| Bore | 82.7 mm |
| Stroke | 93.0 mm |
| Displacement | 1,998 cc |
| Compression ratio | 11.0:1 |
| Rated power | 182 hp DIN @ 6,500 rpm |
| Rated torque | 200 Nm @ 5,250 rpm |
| Rev limiter target | ~7,100-7,250 rpm |

## Repository layout

```text
clio182./
  clio182.mr                         Active development script

docs/
  overview.md                        Project overview
  source-priority.md                 Evidence ranking rules
  methodology.md                     How the engine is being developed
  roadmap.md                         Development plan
  changelog.md                       Human-readable change log

  engine/
    f4r-738-baseline.md              Hard engine data
    f4r-738-head-and-chamber.md      Head, valve and chamber data
    f4r-738-camshaft.md              Cam and dephaser notes
    f4r-738-intake-and-exhaust.md    Breathing system notes
    f4r-738-engine-sim-mapping.md    Real value to .mr mapping
    f4r-738-known-unknowns.md        Data gaps

  validation/
    idle-and-transient-tests.md      Manual stability tests
    dyno-correlation.md              Power/torque targets
    gearbox-and-vehicle.md           Vehicle and JC5 gearing notes

  templates/
    commit-message-template.md
    milestone-entry-template.md
    measurement-log-template.md

data/
  dyno/
    official_factory_targets.csv
  measurements/
    inertia_estimates.csv
```

## Development rule

Change one subsystem at a time. If a change breaks starting, idle, throttle blip recovery or dyno behaviour, revert that change rather than stacking more guesses on top.
