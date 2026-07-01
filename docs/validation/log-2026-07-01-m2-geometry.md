# Validation log - M2.0 geometry lock

## Tested script

```text
clio182./clio182.mr
```

Commit under test:

```text
ff4c93b47a2c9cb19905f862f4404884ae51fd55
```

## User-observed result

```text
Starts with no throttle: yes
Idle: around 800-880 rpm
1500 rpm blip: most stable so far
3000 rpm blip: drops to around 600 rpm, recovers to idle in around 2.5 seconds
Full-throttle blip: stalls
Restart after full-throttle stall: requires holding starter for a few seconds, then idles around 1000 rpm before settling back to previous idle
```

## Interpretation

The M2.0 geometry lock did not break the no-throttle-start baseline. This is good and means the geometry changes are safe to build from.

The full-throttle blip stall remains the main M1 drivability issue.

The delayed restart and temporary high idle after the stall suggests the simulator state after a high-RPM/full-throttle event is not the same as a normal cold start. Likely contributors:

- high-RPM limiter behaviour,
- intake/exhaust transient state,
- excessive airflow/pressure recovery after a snap shut,
- low-rpm catch torque not strong enough after a high-rpm event.

Do not make large intake/inertia changes again. The previous aggressive M1.4 attempt broke no-throttle starting.

## Next action

Make a very small full-throttle recovery experiment while preserving M2.0 start/idle:

- keep geometry untouched,
- keep intake flow untouched,
- keep inertia untouched,
- only adjust limiter/catch behaviour in a small step.
