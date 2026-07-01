# Roadmap

## M1 - Stable reference baseline

Goal: the engine starts and behaves predictably before detailed F4R tuning.

Pass criteria:

- starts with 0 throttle
- warm idle holds for 30 seconds
- 1500 rpm blip returns to idle
- 3000 rpm blip returns to idle
- full-throttle blip does not stall

Current state:

- 1500 and 3000 rpm blip recovery have worked in earlier commits.
- The latest full-throttle recovery attempt broke no-throttle starting.
- Next action: restore the last no-throttle-start script and then approach full-throttle recovery with smaller changes.

## M2 - Hard F4R geometry lock

Lock values that should not be tuned:

- bore 82.7 mm
- stroke 93.0 mm
- rod length 144 mm
- compression height ~30.2 mm
- total clearance volume around 50 cc for 11.0:1 compression

## M3 - Cylinder head baseline

Build a head model around:

- 33.5 mm intake valves
- 29.0 mm exhaust valves
- 10 mm published valve lift
- estimated flow table clearly marked as estimated

## M4 - Camshaft/dephaser variants

Create three separate versions:

- parked inlet dephaser
- advanced inlet dephaser
- mid-phase correlated stock road file

## M5 - Intake and exhaust correlation

Tune intake and exhaust to match the official curve shape without breaking idle stability.

## M6 - Power and torque correlation

Target:

- 182 hp DIN at 6500 rpm
- 200 Nm at 5250 rpm
- realistic 3000-6500 rpm torque shape

## M7 - Sound and drivability

Finalise:

- idle character
- induction tone
- exhaust tone
- rev fall behaviour
- engine braking

## M8 - v1.0 release

Release only when documentation and `.mr` values agree.
