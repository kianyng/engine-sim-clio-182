# Methodology

This project should be developed like an engine calibration project, not by repeatedly guessing whole new scripts.

## Core rule

Only change one subsystem at a time.

Subsystems:

1. starting and idle stability
2. geometry
3. rotating assembly and inertia
4. cylinder head flow
5. camshafts
6. intake
7. exhaust
8. ignition
9. limiter behaviour
10. vehicle and gearbox
11. sound

## Development loop

1. Make one deliberate change.
2. Commit it with the reason.
3. Test using the validation procedure.
4. Record the result.
5. Keep it only if it improves the target behaviour without breaking an earlier milestone.

## What went wrong earlier

Earlier versions changed too many things at once: airflow, cam timing, inertia, idle air, friction and ignition. That made it impossible to know which value caused a start or idle failure.

From now on, if a commit breaks the engine, prefer reverting or narrowing that single change rather than stacking more compensations.

## Current high-priority problem

The latest failed test showed the engine no longer starts without about 0.072 throttle. That means the previous full-throttle blip fix over-corrected the intake/throttle/inertia setup. The next `.mr` work should restore the last no-throttle-start baseline before continuing full-throttle blip recovery tuning.
