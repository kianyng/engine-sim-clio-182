# F4R 738 camshaft and dephaser notes

## What is known

The F4R 738 uses a timing-belt-driven DOHC 16-valve layout with an inlet cam phase shifter/dephaser.

Renault technical material confirms:

- hydraulic tappets
- DOHC layout
- published F4R timing diagrams
- 10 mm valve lift reference
- inlet phase-shifter behaviour

## What is not fully verified

A complete stock F4R 738 cam card is not yet locked.

Still needed:

- intake duration at 0.1 mm / 1.0 mm / 0.050 in
- exhaust duration at 0.1 mm / 1.0 mm / 0.050 in
- intake lobe centre parked
- intake lobe centre advanced
- exhaust lobe centre
- actual lobe shape
- dephaser advance amount under load/RPM

## Current simulator approach

Engine Simulator CE does not expose a complete Renault-style closed-loop cam dephaser strategy through the simple public scripting examples. The practical approach should be to maintain multiple variants:

```text
engines/reference/f4r_738_stock_locked_parked.mr
engines/reference/f4r_738_stock_locked_advanced.mr
engines/reference/f4r_738_stock_midphase_correlated.mr
```

The `midphase_correlated` version is the main demo file. It should be tuned to match the broad real-world torque/power curve, while the locked variants are kept as reference experiments.

## Provisional cam modelling rules

Until a measured stock cam trace is available:

- use around 10 mm lift,
- keep duration moderate,
- avoid race-cam overlap while solving idle,
- tune cam centres using dyno curve shape rather than guessing aggressive numbers.

A good first-pass harmonic lobe should be treated as an approximation, not a claim of exact Renault lobe geometry.
