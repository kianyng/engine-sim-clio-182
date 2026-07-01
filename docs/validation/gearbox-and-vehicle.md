# Gearbox and vehicle notes

## Current simulator vehicle values

The current active script uses approximate Clio 182 road car values:

```mr
mass: 1090 * units.kg
drag_coefficient: 0.35
cross_sectional_area: 2.05 * units.m2
diff_ratio: 4.067
tire_radius: 11.625 * units.inch
```

These are acceptable as a first-pass road-car model, but should be improved later.

## Gear ratios currently used

```mr
1st: 3.727
2nd: 2.048
3rd: 1.393
4th: 1.029
5th: 0.820
Final drive: 4.067
```

These represent a JC5-style five-speed setup for the Clio 182 project.

## Later checks

Validate against:

- road speed per 1000 rpm in each gear
- top speed near the real car's published range
- 0-60 / 0-100 km/h sanity check
- in-gear 30-70 behaviour

Do not over-tune the vehicle model until the engine torque curve is credible.
