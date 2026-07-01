# F4R 738 to Engine Simulator CE mapping

This file separates real Renault data from simulator correlation values.

| Real attribute | `.mr` field | Recommended value | Status | Notes |
|---|---|---:|---|---|
| Bore | `cylinder_bank_parameters.bore` | `82.7 * units.mm` | locked | Hard geometry. |
| Stroke | `crankshaft.throw` | `93.0 * units.mm / 2` | locked | Throw is half stroke. |
| Rod length | `connecting_rod_parameters.length` | `144.0 * units.mm` | high confidence | Keep fixed unless better primary source appears. |
| Compression height | `piston_parameters.compression_height` | `30.2 * units.mm` | medium | Current script still uses 31.0 mm; update later in controlled commit. |
| Deck height | `cylinder_bank_parameters.deck_height` | `stroke/2 + rod_length + compression_height` | derived | Use exact geometry formula. |
| Compression ratio | `cylinder_head.chamber_volume` | `~50.0 * units.cc` | derived | Effective clearance volume for 11.0:1. |
| Valve lift | `harmonic_cam_lobe.lift` | `10.0 * units.mm` | medium-high | Convert to thou/mm consistently. |
| Intake valve diameter | head flow table / CSA | ~33.5 mm | medium | Used to constrain estimated flow. |
| Exhaust valve diameter | head flow table / CSA | ~29.0 mm | medium | Used to constrain estimated flow. |
| Flywheel mass | `crankshaft.flywheel_mass` | ~5.3 kg real basis | medium | CE may need correlated effective inertia. |
| Crank mass | `crankshaft.mass` | ~14.5 kg basis | medium | Use as physical basis, not the only inertia value. |
| Total rotating inertia | `crankshaft.moment_of_inertia` | `~0.052 kg*m^2` equivalent | estimate | CE scripts often use dimensionless numeric inertia; tune carefully. |
| Idle control | `idle_flow_rate`, `idle_throttle_plate_position`, `timing_curve`, inertia | correlated | simulator compensation | CE does not model full Renault closed-loop idle control. |
| Dephaser | cam centre variants | parked / advanced / correlated | simulator approximation | Maintain separate files. |
| Rev limiter | `ignition_module.rev_limit` | 7100-7250 rpm | target | Do not lower permanently just to hide instability. |
| Limiter cut | `limiter_duration` | 0.04-0.08 s | correlated | Too long can worsen post-limiter stall. |

## Current recommendation

Do not continue from the broken no-throttle-start state. Restore the last known no-throttle-start baseline first, then apply the research-backed intake/chamber/cam changes one subsystem at a time.
