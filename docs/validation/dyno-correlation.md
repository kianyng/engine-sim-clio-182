# Dyno correlation

## Official targets

| RPM | Power | Torque | Source level |
|---:|---:|---:|---|
| 5250 | - | 200 Nm | Renault official |
| 6500 | 182 hp DIN | - | Renault official |

## Development rules

Do not tune peak power until the engine starts, idles and survives throttle blips.

A script that makes exactly 182 hp but stalls is not a good model.

## Final correlation target

When the base behaviour is stable:

- peak power within +/- 3% of 182 hp
- peak torque within +/- 5% of 200 Nm
- torque peak around 5250 rpm
- power peak around 6500 rpm
- rev limiter around 7100-7250 rpm
- curve should feel like a naturally aspirated F4R: reasonable midrange, stronger top-end, not a turbo-like torque plateau

## Community dynos

Community dyno data varies heavily because of dyno type, correction method, intake/exhaust modifications, engine health and whether figures are wheel or flywheel corrected.

Use community dynos as a broad shape check, not as a single truth source.
