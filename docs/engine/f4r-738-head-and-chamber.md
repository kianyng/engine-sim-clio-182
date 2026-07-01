# F4R 738 head and chamber

## Known / supported values

| Attribute | Value | Confidence | Notes |
|---|---:|---|---|
| Valvetrain | DOHC, 16 valves, hydraulic tappets | High | F4R technical material. |
| Intake valve diameter | ~33.5 mm | Medium | OE-fit / specialist valve catalogue data. |
| Exhaust valve diameter | ~29.0 mm | Medium | OE-fit / specialist valve catalogue data. |
| Valve lift | ~10.0 mm | Medium-high | Renault technical material gives 10 mm lift for F4R timing data. |
| Chamber-only reference | ~44.3 cc nominal | Medium | Renault Sport R3 assembly material; competition context. |
| Effective CE clearance volume | ~50.0 cc | Derived | Required for 11.0:1 with 499.5 cc swept volume/cylinder. |

## Engine Simulator interpretation

Use `chamber_volume` as the effective clearance-volume input required to produce the correct compression ratio.

Recommended starting point:

```mr
chamber_volume: 50.0 * units.cc
```

Do not blindly use the R3 chamber-only 44.3 cc value as the `.mr` chamber volume unless piston crown, gasket and deck effects are separately represented.

## First-pass head flow philosophy

Until a real flowbench sheet is available, head flow should be estimated conservatively and documented as estimated.

The stock F4R head is a strong 2.0L 16v head, but using race-level flow figures too early causes unrealistic power and makes idle/transient tuning harder.

## Measurement wishlist

- chamber volume with burette and plate
- intake valve throat diameter
- exhaust valve throat diameter
- port minimum cross-sectional area
- flowbench at 28 or 30 inH2O
- valve lift curve from a stock cam and follower setup
