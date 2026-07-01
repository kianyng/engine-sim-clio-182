# Honda B18C5 VTEC reference comparison

Reference file:

```text
assets/reference/05_honda_vtec.mr
```

This file is useful because it is a naturally aspirated DOHC 16-valve inline-4 with similar specific output to the F4R 738. It should be used as an Engine Simulator modelling reference, not as a source of Renault physical dimensions.

## Key B18C5 values found

| Area | B18C5 reference value | Current F4R lesson |
|---|---:|---|
| Displacement | 1.8 L | Similar enough to compare CE modelling technique. |
| Bore/stroke | 81.0 x 87.2 mm | Do not copy; F4R remains 82.7 x 93.0 mm. |
| Chamber volume | 41.6 cc | Close to a high-compression small NA four. F4R effective clearance remains ~50 cc. |
| Starter | 70 lb-ft, -500 rpm | Negative starter speed is worth testing only if direction issues appear. |
| Flywheel mass | 10 lb | Our 28 lb value is a stability correlation value, likely not physical. |
| Crank mass | 35.5 lb | Similar order to F4R estimate. |
| Friction torque | 1 lb-ft | Our 8 lb-ft is high and may be masking other calibration issues. |
| MOI multiplier | 0.5 | Current F4R 0.55 is very close. |
| Plenum volume | 1.325 L | Our 2.2 L M3.0 is still large but much closer than the old 4.5 L. |
| Plenum CSA | 20 cm2 | Our 24 cm2 is reasonable for a 2.0 L first pass. |
| Intake flow | k_carb(800) | F4R M3.0 uses 680; too much restriction may affect power later. |
| Runner flow | k_carb(250) | F4R M3.0 uses 260; close. |
| Runner length | 7 in | F4R M3.0 uses 11 in; reasonable given longer-stroke torque target, but should be tested. |
| Velocity decay | 0.5 | F4R M3.0 uses 0.16; this is a prime experiment target. |
| Exhaust primary | 10 in / k_carb(200) | Honda file uses short/simple exhaust modelling; do not copy blindly. |
| Exhaust volume | 100 L | Clearly a sound/simulation correlation value rather than physical exhaust volume. |
| Low cam | 210/190 deg @ 0.050, 6.9/6.5 mm | Useful low-overlap stable-idle reference. |
| VTEC cam | 240/232 deg @ 0.050, 11.5/10.5 mm | Too aggressive for F4R stock, but useful upper bound. |
| Ignition curve | negative timing values | Sign convention differs from our file; do not copy until verified. |

## What to borrow

Borrow modelling approach, not identity:

- compact plenum rather than oversized stability plenum,
- runner flow around 250-300 carb units,
- high velocity_decay compared with our current value,
- low friction torque as a sanity check,
- moderate base cam timing for idle stability,
- comparison-based experiment logging.

## What not to borrow

Do not copy:

- B18 bore/stroke,
- VTEC valvetrain behaviour,
- 9400 rpm limiter,
- VTEC cam lobes,
- 10 lb flywheel directly,
- Honda firing wire order without checking Renault/CE conventions,
- Honda ignition sign convention.

## Experiment plan suggested by this comparison

Run one-parameter experiments from the current M3.0 intake baseline:

1. `velocity_decay` sweep: 0.16 -> 0.25 -> 0.35 -> 0.50.
2. plenum sweep: 2.2 L -> 1.8 L -> 1.5 L.
3. friction sanity check: 8 lb-ft -> 5 lb-ft -> 2 lb-ft, only after intake sweep.
4. flywheel/MOI sanity check only after friction results.

Success criteria remain:

- starts with no throttle,
- idle stable,
- 1500 and 3000 blips recover,
- 4000 blip no longer stalls,
- full-throttle blip eventually recovers.
