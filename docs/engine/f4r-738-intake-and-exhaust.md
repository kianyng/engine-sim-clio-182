# F4R 738 intake and exhaust notes

## Intake

The stock 182 inlet system is not fully documented in easy public sources. The strongest currently useful anchor is the roughly 60 mm throttle body basis, plus observed Renaultsport manifold behaviour from specialist/community sources.

Recommended first-pass Engine Simulator starting envelope:

```mr
intake intake(
    plenum_volume: 1.7 * units.L,
    plenum_cross_section_area: 28.5 * units.cm2,
    intake_flow_rate: k_carb(650.0),
    runner_flow_rate: k_carb(220.0),
    runner_length: 10.0 * units.inch,
    idle_flow_rate: k_carb(0.22),
    idle_throttle_plate_position: 0.9962,
    velocity_decay: 0.45
)
```

This is a simulator starting point, not a confirmed Renault CAD measurement.

## Exhaust

The stock road manifold dimensions are not yet locked. Renault specialists commonly use longer 4-2-1 style manifold designs for naturally aspirated F4R performance, and Pure Motorsport notes that routing and primary length are important on this platform.

For the stock road simulation, avoid extremely short primaries. Suggested starting band:

- primary length: 22-28 inches
- exhaust volume: 18-25 L
- velocity decay: 0.75-0.95

## Current risk

The latest script broke no-throttle starting after full-throttle blip tuning. The likely cause is that intake decay / max flow / inertia changes were too aggressive and moved the model away from a stable start/idle condition.

## Measurement wishlist

- throttle body ID
- plenum volume by fill or CAD
- runner centreline length
- runner minimum cross-section
- primary tube length and ID
- secondary tube length and ID
- collector dimensions
- catalyst and exhaust volume estimate
