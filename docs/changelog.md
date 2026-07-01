# Changelog

## 2026-07-01 - Repository documentation pass

Added a structured documentation system for the project.

Files added:

- `README.md`
- `docs/overview.md`
- `docs/source-priority.md`
- `docs/methodology.md`
- `docs/roadmap.md`
- `docs/changelog.md`
- engine research files
- validation files
- data templates

Reason:

The project had reached the point where tuning by repeated whole-script replacement was no longer useful. The engine must now be developed with clear separation between real Renault data and Engine Simulator correlation values.

## Earlier tuning notes

The following behaviours were observed during early development:

- Initial generated versions either made far too much power or would not idle.
- A staged reference baseline eventually started and idled without throttle.
- A later calibration recovered from 1500 rpm and 3000 rpm throttle blips.
- A full-throttle blip still stalled.
- The most recent full-throttle fix over-corrected and caused the engine to require about 0.072 throttle to start.

Next `.mr` action:

Restore the last version that started with no throttle, then continue full-throttle blip recovery in smaller increments.
